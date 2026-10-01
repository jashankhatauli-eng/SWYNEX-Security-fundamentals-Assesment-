# SWYNEX Security Fundamentals Assessment

## Task 1: Security Assessment

### Lab Environment
This assessment was performed in an authorized PortSwigger Web Security Academy training lab.

### Security Finding
The blog search functionality was vulnerable to Reflected Cross-Site Scripting (XSS).

### Affected Component
The search input of the blog application.

### Risk
An attacker could inject JavaScript into the application response. If a vulnerable application allowed this in a real-world environment, it could potentially affect users who access a maliciously crafted link.

### Evidence
I tested the search functionality using the authorized training lab payload:

<script>alert(1)</script>

The application displayed a JavaScript alert with the value "1", confirming that the input was executed by the browser.

### Recommended Mitigation
- Properly encode untrusted output according to its HTML context.
- Validate and sanitize user input where appropriate.
- Use a Content Security Policy (CSP) as an additional security layer.
- Avoid inserting untrusted user input directly into HTML.

### Conclusion
The assessment identified a Reflected XSS vulnerability in the authorized training environment. The finding, evidence, risk and recommended mitigations have been documented for Task 1.