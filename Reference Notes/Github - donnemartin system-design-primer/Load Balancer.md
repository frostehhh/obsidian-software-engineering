Load distribution of requests to servers or databases

# Benefits
- Preventing requests from going to unhealthy servers
- Preventing overloading resources
- Helping to eliminate a single point of failure

# Other functionalities
## SSL Termination
## Session Persistence

# Failure Protection
For this, we can set up multiple load balancers in the following modes
[active-passive](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#active-passive) or [active-active](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#active-active)


# Load Balancer Strategies
1. Random
2. Least loaded
3. Session/cookies
4. [Round robin or weighted round robin](https://www.g33kinfo.com/info/round-robin-vs-weighted-round-robin-lb)
5. [Layer 4](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#layer-4-load-balancing)
	Typically checks source IP, destination IP and ports in the header
1. [Layer 7](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#layer-7-load-balancing)
	Checks content of packets


# References
https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#load-balancer