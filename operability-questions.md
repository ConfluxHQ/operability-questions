# Operability Questions - OperabilityQuestions.com

See [`README.md`](README.md) for more details on how to use these questions.

These **operability questions** are useful for helping teams assess the operability of software systems. The operability questions can be used alone or in conjunction with tools like the [Run Book dialogue sheet](http://runbooktemplate.info/) to help discover additional operability criteria or gaps.

Each question requires answers to these key questions: 

* **Who? (What?)**: What kind of user or persona will do this? (Or what kind of system?) 
* **How?**: Which tool (or set of tools) or process will help to do this?
* **Evidence**:  How will you demonstrate this using evidence?
* **Score**: a score of 1 to 5 for how well your approach compares to industry-leading approaches (1 is poor; 5 is excellent)

Use the _Poor_ and _Excellent_ criteria to help guide your scores. These are examples of bad and good extremes; your situation may demand slightly different critera.

> Print this page and record questions using pen & paper with your team

Copyright © 2018 [Conflux Digital Ltd](https://confluxdigital.net/)

Licenced under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) ![CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/3.0/88x31.png)

_Permalink: [OperabilityQuestions.com](http://operabilityquestions.com/)_

## EXAMPLE: How do we trace a call/request end-to-end through the system?

> We need to be able to trace a request across multiple servers/containers/nodes for runtime diagnostic purposes.

### Who?

_The software delivery team and the Web Operations team do this_

### How?

_We use Correlation IDs in HTTP headers, logging the ID at each subsystem, and then searching for the ID in Kibana_

### Evidence 

_We test that Correlation IDs are working properly with BDD tests written in Cucumber. See `tests/correlation-tests` folder e.g. `trace-id.feature`_ 

### Score

_4_

# USABILITY

## USABILITY: Which people or groups do we collaborate with to ensure an effective operator experience? 

> We need a clear understanding of the people and teams that can help to make the software systems work well. 

* Poor: _We fix any operator problems after go-live_
* Excellent: _We collaborate with the live service / operations teams from the start of the project_

### Who?

### How?

### Evidence 

### Score

## USABILITY: How often and in what ways do we collaborate with other teams on operational aspects of the system? At which stages of the development cycle do we assess and meet operational needs?

> We should have a clear approach for meeting the needs of operations people. 

* Poor: _We respond to operational requests after go-live when tickets are raised by the live service teams_
* Excellent: _We collaborate on operational aspects from the very first week of the engagement/project_

### Who?

### How?

### Evidence 

### Score

# VIABILITY

## VIABILITY: What proportion of product budget and team effort is spent addressing operational aspects? How do you track this?

> We should be spending a good proportion of time and effort on addressing operational aspects.

* Poor: _We try to spend as little time and effort as possible on operational aspects / We do not track the spend on operational aspects at all_
* Excellent: _We spend 30% of our time and budget addressing operational aspects_

### Who?

### How?

### Evidence 

### Score

## VIABILITY: What is the longest time between addressing two operational features within your team? That is, what is the longest time between deployments of operationally-focused changes? 

> We should be addressing operational aspects on a regular, frequent basis throughout the project, not occasionally or just at the end of the project.

* Poor: _We do not track operational aspects / It can take months to address operational aspects_
* Excellent: _We deploy changes to address operational aspects as frequently as we deploy changes to address user-visible features_

### Who?

### How?

### Evidence 

### Score

# CONFIGURATON

## CONFIGURATION: How do we know which feature toggles (feature switches) are active for this subsystem?

> We need clarity about the number and nature of feature toggles for a system. Feature toggle need careful management. 

* Poor: _We need to run diffs against config files to determine which feature toggles are arctive_
* Excellent: _We have a simple UI or API to report the active/inactive feature flags in an environment_

### Who?

### How?

### Evidence 

### Score

## CONFIGURATION: How do we deploy a configuration change without redeploying the software?

> We need to be able to change the configuration of software in an environment without redeploying the executable binaries or scripts.

* Poor: _We cannot deploy a configuration change without deploying the software_
* Excellent: _We simply run a config deployment separately from the software_

### Who?

### How?

### Evidence 

### Score

## CONFIGURATION: How do we verify the version and source of the configuration that is being used?

> We need to ensure that only valid, tested configuration data is being used and that the configuration schema itself is controlled. 

* Poor: _We cannot verify the configuration in use_
* Excellent: _We use `sha256sum` hashes to verify the configuration in use_

### Who?

### How?

### Evidence 

### Score

# DIAGNOSIS and TESTABILIY

## DIAGNOSIS: How do we know that the system is healthy (or unhealthy)?

> We need to define simple ways to report health of the system in ways that are meaningful for that system.

* Poor: _We wait for checks made manually by another team to tell us if our software is healthy_
* Excellent: _We query the software using a standard HTTP healthcheck URL, returning HTTP 200/500, etc. based on logic that we write in the code_

### Who?

### How?

### Evidence 

### Score

## DIAGNOSIS: How do we track the main service/system Key Performance Indicators (KPIs)? What are the KPIs? 

> We need to define simple ways to report health of the system in ways that are meaningful for that system.

* Poor: _We do not have service KPIs defined_
* Excellent: _We use logging and/or time series metrics to emit service KPIs that are picked up by a dashboard_

### Who?

### How?

### Evidence 

### Score

## DIAGNOSIS: How do we know that logging is working correctly? 

> Logging is a key aspect of modern software systems and must be working correctly at all times.

* Poor: _We do not test if logging is working_
* Excellent: _We test that logging is working using BDD feature tests that search for specific log message strings after a particular application behaviour is executed_

### Who?

### How?

### Evidence 

### Score

## DIAGNOSIS: How do we know that time series metrics are working correctly? 

> Time series metrics are a key aspect of modern software systems and must be working correctly at all times.

* Poor: _We do not test if time series metrics are working_
* Excellent: _We test that time series metrics are working using BDD feature tests that search for specific time series data after a particular application behaviour is executed_

### Who?

### How?

### Evidence 

### Score

## TESTABILITY: How do we show that the software system is easy to test? What do we provide and to whom? 

> Keeping software testable is a key aspect of operability. 

* Poor: _We do not explicitly aim to make out software easily testable_
* Excellent: _We run clients and external test packs against all parts of our software within our deployment pipeline_

### Who?

### How?

### Evidence 

### Score

# SECURITY AND SECURABILITY

## SECURITY: How do we know when an SSL/TLS certificate is close to expiry?

> We need to have clarity about certificate renewal so we avoid systems breaking due to expired certificates.

* Poor: _We do not know when our certificates are going to expire_
* Excellent: _We use certificate monitoring tools to keep a live check on when certs will expire so we can take remedial action ahead of time_

### Who?

### How?

### Evidence 

### Score

## SECURITY: How are SSL/TLS certificates renewed?

> We need to have clarity about certificate renewal so we avoid systems breaking due to expired certificates.

* Poor: _Another team renews and installs SSL/TLS certificates manually_
* Excellent: _We use automated processes to renew and configure SSL/TLS certificates using *Let's Encrypt*_

### Who?

### How?

### Evidence 

### Score

## SECURITY: How are non-HTTPS certificates and other security keys renewed?

> We need to have clarity about certificate renewal so we avoid systems breaking due to expired certificates.

* Poor: _Another team renews and installs certificates manually_
* Excellent: _We use automated processes to renew and configure certificates using an API_

### Who?

### How?

### Evidence 

### Score

## SECURITY: How do we ensure that data in transit is encrypted?

> We need to encrypt data in transit to prevent eavesdropping.

* Poor: _We do not explicitly test for transport security; we assume that another team will configure security for us_
* Excellent: _We test for secure transport as a specific feature of our application_

### Who?

### How?

### Evidence 

### Score

## SECURITY: How do we ensure that sensitive data in logs is masked or hidden?

> We need to mask or hide sensitive data in logs whilst still exposing the surrounding data to teams.

* Poor: _We do not test for data masking in logs_
* Excellent: _We test that data masking is happening by using BDD feature tests that search for specific log message strings after a particular application behaviour is executed_

### Who?

### How?

### Evidence 

### Score

## SECURABILITY: How do we patch public-facing systems safely when a Zero-Day Vulnerability is found?

> We need to apply patches to public-facing systems as quickly as possible (but still safely) when a Zero-Day vulnerability is disclosed.

* Poor: _Another team is responsible for patching / We do not know if or when a Zero-Day vulnerability occurs_
* Excellent: _We work with the security team to test and roll out a fix, using our automated deployment pipeline to test and deploy the change_

### Who?

### How?

### Evidence 

### Score

# PERFORMANCE

## PERFORMANCE: How do we know that the system/service performs within acceptable ranges?

> We need to demonstrate that the software can perform well.

* Poor: _We rely on the Performance team to validate the performance of our service or application_
* Excellent: _We run a set of indicative performance tests within our deployment pipeline that are run on every check-in to version control_

### Who?

### How?

### Evidence 

### Score

# RELIABILITY, REPEATABILITY, RESILIENCE

## RELIABILITY: How can we see and share the different known failure modes for the system?

> We need to define and share a set of known failure modes or failure conditions so we better understand how the software will operate.

* Poor: _We do not really know how the system might fail_
* Excellent: _We use a set of error identifiers to define the failure modes in our software and we use these identifiers in our log messages_

### Who?

### How?

### Evidence 

### Score

## RESILIENCE: How are we sure that connection retry schemes (such as Exponential Backoff) are working?

> We need to demonstrate that the system does not overload downstream systems with reconnection attempts, and uses sensible back-off schemes.

* Poor: _We do not really know whether connection retry works properly_
* Excellent: _We test the connection retry logic as part of our automated deployment pipeline_

### Who?

### How?

### Evidence 

### Score

# OBSERVABILITY

## OBSERVABILITY: How do we trace a call/request end-to-end through the system?

> We need to be able to trace a request across multiple servers/containers/nodes for runtime diagnostic purposes.

* Poor: _We do not trace calls through the system_
* Excellent: _We use a standard tracing library such as OpenTracing to trace calls through the system. We collaborate with othher teams to ensure that the correct tracing fields are maintained across component boundaries_

### Who?

### How?

### Evidence 

### Score

## OBSERVABILITY: How do we display the current service/system status to operations-facing teams?

> We need to display key information about the live operation of the system to teams focused on operations.

* Poor: _Operations teams tend to discover the status indicators themselves_
* Excellent: _We build a dashboard in collaboration with the Operations teams so they have all the details they need in a user-friendly way with UX a key consideration_

### Who?

### How?

### Evidence 

### Score

## OBSERVABILITY: How accurate is the Synthetic Monitoring for key service or user scenarios?

> We need to run synthetic transactions against the live systems on a regular basis. How well does the synthetic monitoring detect problems?

* Poor: _The service often goes down without us knowing, and users inform us before we detect a problem / We do not have synthetic monitoring in place for key scenarios_
* Excellent: _The synthetic monitoring alerts us quickly to problems with key journeys or scenarios_

### Who?

### How?

### Evidence 

### Score

# RECOVERY

## RECOVERY: How do we know that the system/service will recover from an internal failure?

> We need to demonstrate that the software can recover from internal failures gracefully.


* Poor: _We do not really know whether the system can recover from internal failures_
* Excellent: _We test many internal failure scenarios as part of our automated deployment pipeline_

### Who?

### How?

### Evidence 

### Score

## RECOVERY: How do we know that the system/service will recover from an external failure?

> We need to demonstrate that the software can recover from external failures gracefully.

* Poor: _We do not really know whether the system can recover from external failures_
* Excellent: _We test many external failure scenarios as part of our automated deployment pipeline_

### Who?

### How?

### Evidence 

### Score

# SAFETY and ETHICS

> Note: operability does not guarantee safety or ethical soundness. Discuss and follow up separately.

## SAFETY: How do we know that the system is safe to operate in different failure modes?

> Note: operability does not guarantee safety. Discuss and follow up separately.

### Discussion 

## ETHICS: How do we know that the system is ethically sound?

> Note: operability does not guarantee ethical operation. Discuss and follow up separately.

### Discussion 

