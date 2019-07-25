# azure-cdn-ips

This repository contains 4 files that are updated daily based off of the contents from the [Azure CDN Edge Nodes List](https://docs.microsoft.com/en-us/rest/api/cdn/edgenodes/list). Azure decided that this IP list should be behind authentication instead of publicly available compared to [Azure IP Ranges and Service Tags](https://www.microsoft.com/en-us/download/details.aspx?id=56519)

  - edgenodes.json - raw JSON pulled from the Azure API
  - edgenodes-ipv4.txt - parsed, sorted, and unique IPv4 subnets
  - edgenodes-ipv6.txt - parsed, sorted, and unique IPv6 subnets
  - lastrun - date the script last ran

The bash script that updates this repository is located in [get-azure-cdn-ips](https://github.com/Gelob/get-azure-cdn-ips)

### Usage
You should not use this list to directly feed a firewall without doing your own validation.

### Notes
The bash script that runs is very basic but it does have a few simple protections built into it to ensure bad data doesn't get updated to this repoistory. Time will tell if they are enough.
 1. If we can't authenticate to the API or Azure returns an error, the script aborts
 2. If the IPv4 list doesn't contain a subnet at the start or end of the list, the script aborts.

### Community
Want to contribute, or have comments? Feel free to open an [issue](https://github.com/Gelob/azure-cdn-ips/issues/new)

### License
[Clear BSD License](https://github.com/Gelob/azure-cdn-ips/blob/master/LICENSE)
