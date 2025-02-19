name: TryHackMe Update Badge

on:
  schedule:
    # Make it run every 24 hour
    - cron: '0 0 * * *'
  workflow_dispatch:
jobs:
  tryhackme-badge-update:
    name: Update this repo's tryhackme badge with the latest tryhackme image badge
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: p4p1/tryhackme-badge-workflow@main
        with:
          # Replace with your tryhackme username
          username: "<y0pi>"
          GITHUB_TOKEN: ${{secrets.GITHUB_TOKEN}} # Do not paste your github token here - this is a placeholder
                                                  # and will pull your github token automatically
![tryhackme stats](https://raw.githubusercontent.com/<y0pi>/<y0pi>/master/assets/thm_propic.png)
