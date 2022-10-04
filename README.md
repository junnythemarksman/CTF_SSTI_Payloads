# Server-Side Template Injection (SSTI)
A small collection of SSTI Payloads from the internet.

# What is SSTI
<a href='https://book.hacktricks.xyz/pentesting-web/ssti-server-side-template-injection'>Please refer to Hacktricks</a>

# Payloads :
To test for vulnerability, try these each of the payloads below. The expected result should be the multiplication of 7 and 7 which is equal to 49.
```
{{7*7}}
${7*7}
<%= 7*7 %>
${{7*7}}
#{7*7}
*{7*7}
```
