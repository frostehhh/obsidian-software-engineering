# Mockito — Study Summary

> Source: [Baeldung Learn Mockito Course](https://www.baeldung.com/members/courses/learn-mockito)

---

## Core Concepts

**Mocks vs Stubs**
- **Stub** — an object that returns a predefined response for a method call
- **Mock** — an object that simulates behavior; may use stubs internally

Mockito combines both concepts. Understanding the distinction is still useful, even though Mockito blurs the line in practice.

---

## Module 1 — Introduction to Unit Testing and Mockito

### Stubbing Methods

- Unstubbed methods that return values fall back to Java defaults: `null`, `0`, empty collections, etc.
- Use `when(...).thenReturn(...)` to stub a value-returning method.
- For void methods, explicitly stub with `doNothing()` to make intent clear and catch future signature changes.
- Use **consecutive `thenReturn()`** calls when a method should return different values on repeated invocations:

```java
when(taskRepository.findById(1L))
    .thenReturn(sampleTask)
    .thenReturn(sampleTask2)
    .thenReturn(sampleTask3);
```

**Argument Matchers**
- Use `any*()` helpers (e.g. `anyLong()`, `anyString()`) when the exact argument value doesn't matter.
- You cannot mix exact values and argument matchers — wrap exact values in `eq()` instead.
- Full list: https://site.mockito.org/javadoc/current/org/mockito/ArgumentMatchers.html

### Verifying Interactions

Mockito can assert that specific methods were (or were not) called with specific arguments.

| Method | Purpose |
|---|---|
| `verify(mock).method(args)` | Assert method was called once |
| `verify(mock, times(n)).method(args)` | Assert called exactly n times |
| `verify(mock, never()).method(args)` | Assert never called |
| `inOrder.verify(mock).method(args)` | Assert call order |

Same argument matcher rules apply — cannot mix exact values with matchers without `eq()`.

---

## Module 2 — Advanced Mockito Techniques

### Spies (Partial Mocks)

A **spy** wraps a real object — real methods run by default, but individual methods can still be stubbed.

```java
@Spy
DefaultCampaignService campaignService;

CampaignRepository spyRepository = spy(new InMemoryCampaignRepository());
```

- Prefer spies when you need to test the real implementation of a class.
- If you find yourself stubbing most methods on a spy, consider simplifying the implementation instead.

### Advanced Stubbing

**`thenAnswer()`** — dynamic return values based on input arguments:

```java
when(taskRepository.findById(any())).thenAnswer(invocation -> {
    Long id = invocation.getArgument(0);
    return switch (id.intValue()) {
        case 1 -> Optional.of(aTask("Task 1"));
        case 2 -> Optional.of(aTask("Task 2"));
        default -> Optional.empty();
    };
});
```

**`doAnswer()`** — simulate side effects in void-returning methods:

```java
doAnswer(invocation -> {
    Task taskArg = invocation.getArgument(0);
    taskArg.setId(null);
    return null;
}).when(taskRepository).delete(task);
```

**Deep Stubbing** — stub a chain of method calls concisely. Use sparingly — hides design issues and creates brittle tests:

```java
TaskRepository taskRepository = mock(TaskRepository.class, Mockito.RETURNS_DEEP_STUBS);

when(taskRepository.getById(1L)
    .getAssignee()
    .getFirstName()
).thenReturn("John");
```

### Exception Handling

```java
// Value-returning method
when(campaignRepository.findById(1L)).thenThrow(new IllegalStateException("DB failure"));

// Void method
doThrow(new IllegalStateException("Can't delete")).when(campaignRepository).deleteById(eq(1L));

// Asserting an exception is thrown
assertThrows(IllegalStateException.class, () -> campaignService.deleteCampaign(1L));
```

### ArgumentCaptor

Captures arguments passed to a mocked method for detailed inspection and assertion.

- **Differs from `doAnswer()`**: `doAnswer()` is for mocking side effects; `ArgumentCaptor` is for verifying what was passed.
- See: https://site.mockito.org/javadoc/current/org/mockito/ArgumentCaptor.html

---

## Quick Reference — When to Use What

| Scenario | Tool |
|---|---|
| Return a fixed value | `when().thenReturn()` |
| Return different values on repeated calls | Chained `thenReturn()` |
| Return value based on input | `thenAnswer()` |
| Simulate a void side effect | `doAnswer()` |
| Throw an exception (value method) | `thenThrow()` |
| Throw an exception (void method) | `doThrow()` |
| Assert a method was called | `verify()` |
| Assert call order | `inOrder.verify()` |
| Inspect what argument was passed | `ArgumentCaptor` |
| Test real implementation with selective stubbing | `spy()` / `@Spy` |
