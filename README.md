# ddev-zap-elk

Automated security tests for DDEV

You can integrate these results with your own reporting tool, but we like ELK :). 
It creates a **html**,**xml** and a **json** file, therefore, any CI tool integration is easy.


## Requirements

* Docker
* Docker-compose


## Usage

Just pass URL Parameter to the script. The scan can take more than 30 mins. because of the web crawler (Spider).

```shell
./run-docker-baseline.sh https://www.example.com/
```

1) Testing will run against the host. Estimated times are below, but are highly dependent on the size of your project / site:

Baseline Scan: <2 mins
Extended Scan: <10 mins
Full active scan: ~30mins

2) View static results
Static HTML showing test results and suggested corrective actions can be found in the repo. Exmaple: View output.html in the local repo

3) View searchable results in Kibana. ELK is launched after the tests complete and will be running on port 5601. Browse to: http://localhost:5601  (username: elastic, pass: changeme)

<img src="zap-proxy.gif?raw=true" width="1080px">
