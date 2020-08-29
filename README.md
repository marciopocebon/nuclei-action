# Dynamic Application Security Testing (DAST) with Nuclei

# Usage
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
