name: Generate Batman Snake

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:
  push:
    branches:
    - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: Generate github-contribution-grid-snake.svg
        uses: Platane/snk@v3
        with:
          github_user_name: Nishanth0072
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark&color_snake=#ffd700&color_dots=#0d0d0d,#1a1a1a,#2d2d2d,#4a4a4a,#ffd700

      - name: Push github-contribution-grid-snake.svg to output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
