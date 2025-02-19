name: Update TryHackMe Badge

on:
  schedule:
    - cron: '0 0 * * *' # Runs every day at midnight
  workflow_dispatch: # Allows manual triggering

jobs:
  update-badge:
    runs-on: ubuntu-22.04

    steps:
    - name: Checkout repository
      uses: actions/checkout@v2

    - name: Configure Git Identity
      run: |
        git config --global user.name "GitHub Actions Bot"
        git config --global user.email "actions@github.com"

    - name: Fetch TryHackMe Badge
      uses: DhanushNehru/tryhackme-badge-action-workflow@v1.0
      with:
        image_path: './assets/tryhackme-badge.png'
        username: 'y0pi'
        user_id: '<iframe src="https://tryhackme.com/api/v2/badges/public-profile?userPublicId=1157207" style='border:none;'></iframe>'
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
