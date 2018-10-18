# "Threat Modeling Python Web Apps Written with Flask and Django" by [Jared Smith](https://www.twitter.com/jaredthecoder)


## Threat Modeling
Think of threat modeling as a house with jewelry inside that you want to protect
Doors are a feature, but can be a security vulnerability

## Know your system

Draw grockable diagrams
* Trust boundaries–example: search form where the input from a user goes to another layer like a QuerySet or cache
* Data flow–example: authentication microservice that receives data from a front-end application
* Entry points–example: Front-end interface, microservice calls, management interfaces, backend services like cache
* Privileged code/areas–example: file that makes some system calls

## Know your threats

### Motivations for finding vulnerabilities
* Black, white, grey hat
* Money, power, destruction, revenge, politics
* Morality, responsibility, helping other people

### Ways vulnerabilities are found
* Accidental discovery
* The curious attacker
* Script kiddies
* Motivated attacker
* Organized crime
* Nation state

## Prioritize and Fix

* Assign score of likelihood to exploit
* Assign impact
* Risk = likelihood x impact

### Common Vulnerabilities in Flask and Django

* SQL injection-mitigation: sanitize user input and use parameterization. Use ORM
* Command injection, remote code execution–mitigation: sanitize!
* XSS, client-side scripts, reflected XSS-mitigation: sanitize, use appropriate security headers (CSP, etc)
* CSRF–mitigation: don't allow GET to have side-effects, unique tokens for submitted data
* Insecure credential storage, bad session management–mitigation: use built-in session frameworks
* Use secure hashing, compression
* Update dependencies often
* Collect all logs

### Summary

* Identify assets
* Understand application
* Identify threats and vulnerabilities
* Prioritize and fix issues
