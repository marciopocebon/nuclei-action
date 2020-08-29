<h1 align="left">
  <img src="https://github.com/projectdiscovery/nuclei/blob/master/static/nuclei-logo.png" alt="nuclei" width="200px"></a>
  <br>
</h1>

[Nuclei](https://github.com/projectdiscovery/nuclei) is an open-source web application security scanner developed by [ProjectDiscovery.io](https://twitter.com/pdiscoveryio).
Its template engine empowers a community of cybersecurity researchers to keep up to date with the latest security exploits.

## Usage
```
name: "Dynamic Application Security Testing (DAST) with Nuclei"

on:
  workflow_dispatch:
  schedule:
    - cron: "0 10 * * *"

jobs:
  worker:
    runs-on: ubuntu-latest
    name: nuclei
    steps:
      - uses: actions/checkout@master
      - uses: aqme/nuclei-action@master
        with:
          urls-txt: ".github/nuclei.txt"
          slack-token: ${{ secrets.SLACK_TOKEN }}
          slack-channel: ${{ secrets.SLACK_CHANNEL_NUCLEI }}
          dd-api-key: ${{ secrets.DD_API_KEY }}
```
