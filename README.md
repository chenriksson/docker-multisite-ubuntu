# Deploy DockerExtension on Ubuntu (POC)

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fchenriksson%2Fdocker-multisite-ubuntu%2Fmaster%2Fazuredeploy2.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>
<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fchenriksson%2Fdocker-multisite-ubuntu%2Fmaster%2Fazuredeploy2.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

This template installs DockerExtension on single Ubuntu VM behind a NLB.

Public IP provided for HTTP/80 and SSH/22 access directly to VM:
- {dnsLabelPrefix}.{region}.cloudapp.azure.com

3 additional public IPs are provided on the NLB with the following rules:
- {dnsLabelPrefix}0.{region}.cloudapp.azure.com
  - port 80 => 8000
  - port 18010 => 18000
- {dnsLabelPrefix}1.{region}.cloudapp.azure.com
  - port 80 => 8001
  - port 18010 => 18001
- {dnsLabelPrefix}2.{region}.cloudapp.azure.com
  - port 80 => 8002
  - port 18010 => 18002
