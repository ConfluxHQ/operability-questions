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

## EXAMPLE: How do we trace a call end-to-end through the system?

> This question addresses ...

### Who?

_The software delivery team and the Web Operations team do this_

### How?

_We use Correlation IDs in HTTP headers, logging the ID at each subsystem, and then searching for the ID in Kibana_

### Evidence 

_We test that Correlation IDs are working properly with BDD tests written in Cucumber. See `tests/correlation-tests` folder e.g. `trace-id.feature`_ 

# CONFIGURATON

## CONFIGURATION: How do we know which feature toggles (feature switches) are active for this subsystem?

> This question addresses the need for clarity about the number and nature of feature toggles for a system. Feature toggle need careful management. 

### Who?

### How?

### Evidence 

## CONFIGURATION: How do we deploy a configuration change without redploying the software?

> This question addresses ...

### Who?

### How?

### Evidence 

# SECURITY

## SECURITY: How do we know when an SSL/TLS certificate is close to expiry?

> This question addresses ...

### Who?

### How?

### Evidence 

## SECURITY: How are SSL/TLS certificates renewed?

> This question addresses ...

### Who?

### How?

### Evidence 

## SECURITY: How are non-HTTPS certificates and other security keys renewed?

> This question addresses ...

### Who?

### How?

### Evidence 

## SECURITY: How do we ensure that data in transit is encrypted?

> This question addresses ...

### Who?

### How?

### Evidence 

## SECURITY: How do we patch public-facing systems safely when a Zero-Day Vulnerability is found?

> This question addresses ...

### Who?

### How?

### Evidence 

