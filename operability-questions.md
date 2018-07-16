# Operability Questions

See [`README.md`](README.md) for more details on how to use these questions.

These **operability questions** are useful for assessing the operability of software systems. The operability questions can be used alone or in conjunction with tools like the [Run Book dialogue sheet](http://runbooktemplate.info/) to help discover additional operability criteria or gaps.

Each question requires answers to these key questions: 

* **Who? (What?)**: What kind of user or persona will do this? (Or what kind of system?) 
* **How?**: Which tool (or set of tools) or process will help to do this?
* **Evidence**:  How will you demonstrate this using evidence?

> Print this page and record questions using pen & paper with your team

Copyright © 2018 [Conflux Digital Ltd](https://confluxdigital.net/)

Licenced under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) ![CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/3.0/88x31.png)

## EXAMPLE: How do we trace a call/request end-to-end through the system?

> We need to be able to trace a request across multiple servers/containers/nodes for runtime diagnostic purposes.

### Who?

_The software delivery team and the Web Operations team do this_

### How?

_We use Correlation IDs in HTTP headers, logging the ID at each subsystem, and then searching for the ID in Kibana_

### Evidence 

_We test that Correlation IDs are working properly with BDD tests written in Cucumber. See `tests/correlation-tests` folder e.g. `trace-id.feature`_ 

# CONFIGURATON

## CONFIGURATION: How do we know which feature toggles (feature switches) are active for this subsystem?

> We need clarity about the number and nature of feature toggles for a system. Feature toggle need careful management. 

### Who?

### How?

### Evidence 

## CONFIGURATION: How do we deploy a configuration change without redploying the software?

> We need to be able to change the configuration of software in an environment without redeploying the executable binaries or scripts.

### Who?

### How?

### Evidence 

## CONFIGURATION: How do we verify the version and source of the configuration that is being used?

> We need to ensure that only valid, tested configuration data is being used and that the configuration schema itself is controlled. 

### Who?

### How?

### Evidence 

# DIAGNOSIS and TESTABILIY

## DIAGNOSIS: How do we know that the system is healthy (or unhealthy)?

> We need to define simple ways to report health of the system in ways that are meaningful for that system.

### Who?

### How?

### Evidence 

## DIAGNOSIS: How do we track the main service/system Key Performance Indicators (KPIs)? What are the KPIs? 

> We need to define simple ways to report health of the system in ways that are meaningful for that system.

### Who?

### How?

### Evidence 

## DIAGNOSIS: How do we know that logging is working correctly? 

> Logging is a key aspect of modern software systems and must be working correctly at all times.

### Who?

### How?

### Evidence 

## DIAGNOSIS: How do we know that time series metrics are working correctly? 

> Time series metrics are a key aspect of modern software systems and must be working correctly at all times.

### Who?

### How?

### Evidence 

## TESTABILITY: How do we show that the software system is easy to test? What do we provide and to whom? 

> Keeping software testable is a key aspect of operability. 

### Who?

### How?

### Evidence 


# SECURITY AND SECURABILITY

## SECURITY: How do we know when an SSL/TLS certificate is close to expiry?

> We need to have clarity about certificate renewal so we avoid systems breaking due to expired certificates.

### Who?

### How?

### Evidence 

## SECURITY: How are SSL/TLS certificates renewed?

> We need to have clarity about certificate renewal so we avoid systems breaking due to expired certificates.

### Who?

### How?

### Evidence 

## SECURITY: How are non-HTTPS certificates and other security keys renewed?

> We need to have clarity about certificate renewal so we avoid systems breaking due to expired certificates.

### Who?

### How?

### Evidence 

## SECURITY: How do we ensure that data in transit is encrypted?

> We need to encrypt data in transit to prevent eavesdropping.

### Who?

### How?

### Evidence 

## SECURITY: How do we ensure that sensitive data in logs is masked or hidden?

> We need to mask or hide sensitive data in logs whilst still exposing the surrounding data to teams.

### Who?

### How?

### Evidence 


## SECURABILITY: How do we patch public-facing systems safely when a Zero-Day Vulnerability is found?

> We need to apply patches to public-facing systems as quickly as possible (but still safely) when a Zero-Day vulnerability is disclosed.

### Who?

### How?

### Evidence 

# PERFORMANCE

## PERFORMANCE: How do we know that the system/service performs within acceptable ranges?

> We need to demonstrate that the software can perform well.

### Who?

### How?

### Evidence 

# RELIABILITY, REPEATABILITY, RESILIENCE

## RELIABILITY: How can we see and share the different known failure modes for the system?

> We need to define and share a set of known failure modes or failure conditions so we better understand how the software will operate.

### Who?

### How?

### Evidence 


## RESILIENCE: How are we sure that connection retry schemes (such as Exponential Backoff) are working?

> We need to demonstrate that the system does not overload downstream systems with reconnection attempts, and uses sensible back-off schemes.

### Who?

### How?

### Evidence 


# OBSERVABILITY

## OBSERVABILITY: How do we trace a call/request end-to-end through the system?

> We need to be able to trace a request across multiple servers/containers/nodes for runtime diagnostic purposes.

### Who?

### How?

### Evidence 

## OBSERVABILITY: How do we display the current service/system status to operations-facing teams?

> We need to display key information about the live operation of the system to teams focused on operations.

### Who?

### How?

### Evidence 


# RECOVERY

## RECOVERY: How do we know that the system/service will recover from an internal failure?

> We need to demonstrate that the software can recover from internal failures gracefully.

### Who?

### How?

### Evidence 

## RECOVERY: How do we know that the system/service will recover from an external failure?

> We need to demonstrate that the software can recover from external failures gracefully.

### Who?

### How?

### Evidence 


# SAFETY and ETHICS

> Note: operability does not guarantee safety or ethical soundness. Discuss and follow up separately.

## SAFETY: How do we know that the system is safe to operate in different failure modes?

> Note: operability does not guarantee safety. Discuss and follow up separately.

### Discussion 

## ETHICS: How do we know that the system is ethically sound?

> Note: operability does not guarantee ethical operation. Discuss and follow up separately.

### Discussion 

