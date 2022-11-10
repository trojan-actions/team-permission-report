## team permission report
### Usage: 

```yml
name: Repo dormancy report
on:
  schedule:
    # Runs on the first day of the month at 00:00 UTC
    #
    #        ┌────────────── minute
    #        │ ┌──────────── hour
    #        │ │ ┌────────── day (month)
    #        │ │ │ ┌──────── month
    #        │ │ │ │ ┌────── day (week)
    - cron: '0 0 1 * *'
  workflow_dispatch:
jobs:
  dormant-repos:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: Get dormant repos
        uses: gusshawstewart/team-permission-report@v2.0
        with:
          token: ${{ secrets.ORG_TOKEN }}
```
