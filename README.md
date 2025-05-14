Olá, eu sou o Daniel Soares 👋
Sou aluno do Instituto Proa e estou no último ano do Ensino Médio. Apaixonado por tecnologia, busco sempre aprender novas ferramentas e aprimorar meus conhecimentos em programação e desenvolvimento.

💻 Tecnologias que estou aprendendo:

Java, JavaScript, HTML, CSS, e SQL

Desenvolvimento Web (React, Node.js)

Banco de Dados (SQL, NoSQL)

Inteligência Artificial

🚀 Objetivo: Me tornar um desenvolvedor completo e contribuir com a comunidade de código aberto.

📫 Me encontre em:

Email: danielsoares300907@gmail.com

LinkedIn: Daniel Soares

![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=danielsoares30&show_icons=true&theme=dark)

[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black&background=1d1f21)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=MySQL&logoColor=white&background=1d1f21)](https://www.mysql.com/)
[![HTML](https://img.shields.io/badge/HTML-E34F26?style=flat&logo=html5&logoColor=white&background=1d1f21)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS](https://img.shields.io/badge/CSS-1572B6?style=flat&logo=css3&logoColor=white&background=1d1f21)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![Java](https://img.shields.io/badge/Java-007396?style=flat&logo=java&logoColor=white&background=1d1f21)](https://www.java.com/)


name: GitHub-Profile-3D-Contrib

on:
  schedule: # 03:00 JST == 18:00 UTC
    - cron: "0 18 * * *"
  workflow_dispatch:

permissions:
  contents: write

jobs:
  build:
    runs-on: ubuntu-latest
    name: generate-github-profile-3d-contrib
    steps:
      - uses: actions/checkout@v4
      - uses: yoshi389111/github-profile-3d-contrib@latest
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          USERNAME: ${{ github.repository_owner }}
      - name: Commit & Push
        run: |
          git config user.name github-actions
          git config user.email github-actions@github.com
          git add -A .
          if git commit -m "generated"; then
            git push
          fi
