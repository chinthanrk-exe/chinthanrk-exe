# :magic_wand:Who Am I ?

Passionate about technology, programming, and open-source.<br>Currently learning and improving my skills in: Python,Java,HTML,etc...<br> Interested in software development, automation, Discord development, and creating useful projects.<br>Always learning, building, and exploring new technologies.


## 🌊Connect ?
[![Instagram](https://img.shields.io/badge/Instagram-%23E4405F.svg?logo=Instagram&logoColor=white)](https://instagram.com/chinthanrk_) [![LinkedIn](https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white)](https://linkedin.com/in/https://www.linkedin.com/in/chinthan-rk-2537aa419?utm_source=share_via&utm_content=profile&utm_medium=member_android) [![email](https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white)](mailto:chinthanrk6@gmail.com) 

# 🛠️Tech Arsenal !
name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

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
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg?palette=github-dark


      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: snake-output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}


<!-- Proudly created with GPRM ( https://gprm.itsvg.in ) -->
