
Hi! Thanks for dropping by:

Here you can follow along  with the stream or have access to the code or project I'm working on.

<!---
cantidosan/cantidosan is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# Visit https://github.com/lowlighter/metrics/blob/master/action.yml for full reference
name: Metrics
on:
  # Schedule updates (each hour)
  schedule: [{cron: "0 * * * *"}]
  # Lines below let you run workflow manually and on each commit
  workflow_dispatch:
  push: {branches: ["master", "main"]}
jobs:
  github-metrics:
    runs-on: ubuntu-latest
    steps:
      - uses: lowlighter/metrics@latest
        with:
          # Your GitHub token
          token: ${{ secrets.METRICS_TOKEN }}

          # Options
          user: cantidosan
          template: classic
          base: header, activity, community, repositories, metadata
          config_timezone: America/Toronto
          plugin_languages: yes
          plugin_languages_analysis_timeout: 15
          plugin_languages_categories: markup, programming
          plugin_languages_colors: github
          plugin_languages_limit: 8
          plugin_languages_recent_categories: markup, programming
          plugin_languages_recent_days: 14
          plugin_languages_recent_load: 300
          plugin_languages_sections: most-used
          plugin_languages_threshold: 0%
          plugin_tweets: yes
          plugin_tweets_limit: 2
          plugin_tweets_user: .user.twitter
