# Security testing and DDEV-Local

DevSecOps has become a movement that, amongst other things, shifts security awareness and testing ‘left’, to be incorporated earlier and continuously throughout the SDLC. It empowers developers to test for security flaws, primarily using Dynamic Application Security Testing (DAST) tools, and view the results in real-time. This minimizes the impact of discovering security flaws and allows for a less painful correction in the latter stages of development. 

DDEV-Local enables developers to get up and working on projects faster, and DDEV-Live offers scalable infrastructure to seamlessly run those applications at scale. As part of the development process the DDEV team now offers a framework that allows developers to test for security flaws and review those results at any stage of their development, from the first line of code through to testing as part of the build. 


## Requirements

* Docker
* Docker-compose


## Usage

Just pass a URL to any one of the three scripts. 

Baseline Scan
```shell
./run-docker-baseline.sh https://www.example.com/
```
Tools: OWASP ZAP (baseline.py), nmap 

or
```shell
./run-docker-extended.sh https://www.example.com/
```
Tools: OWASP-ZAP, nmap, Nikkto, sqlmap,

or
```shell
./run-docker-full.sh https://www.example.com/
```
Tools: OWASP-ZAP, nmap, Nikkto, sqlmap, owasp-depenency-check



1) Testing will run against the host. Estimated times are below, but are highly dependent on the size of your project / site:

Baseline Scan: <2 mins
Extended Scan: <10 mins
Full active scan: ~30mins

2) View static results
Static HTML showing test results and suggested corrective actions can be found in the repo. Exmaple: View output.html in the local repo

<img src="zap-scan-results.pdf?raw=true" width="1080px">

3) View searchable results in Kibana. ELK is launched after the tests complete and will be running on port 5601. Browse to: http://localhost:5601  (username: elastic, pass: changeme)

<img src="zap-proxy.gif?raw=true" width="1080px">
