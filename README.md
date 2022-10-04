# Server-Side Template Injection (SSTI)
A simple tutorial of SSTI commonly used in Capture The Flag (CTF). It is a guide to detect SSTI and possibly obtain remote code exection (RCE) on the server.

# Detect if the server is vulnerable to SSTI:
To test for vulnerability, try these each of the payloads below. The expected result should be the multiplication of 7 and 7 which is equal to 49. If one of the payloads return the expected result (i.e. 49), then the server is vulnerable to SSTI.
```
{{7*7}}
${7*7}
<%= 7*7 %>
${{7*7}}
#{7*7}
*{7*7}
```
