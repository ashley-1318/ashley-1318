<div align="center">

  <p><img src="https://komarev.com/ghpvc/?username=YOUR_GITHUB_USERNAME&style=flat-square&color=blueviolet" alt="profile visitors"/></p>
  
  <a href="https://www.linkedin.com/in/ashley-josco-c" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn Badge"/>
  </a>
  <a href="https://ashley-portfolio-62b1b.web.app/" target="_blank">
    <img src="https://img.shields.io/badge/Portfolio-FFCA28?style=for-the-badge&logo=firebase&logoColor=black" alt="Portfolio Badge"/>
  </a>
  <a href="mailto:ashleyjosco18@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail Badge"/>
  </a>
  
</div>

---

<table>
<tr>
<td valign="top" width="60%">

### Hey there, I'm Ashley! 👋

I'm a passionate developer and innovator, transforming complex problems into intelligent solutions through the power of AI and Machine Learning.

```javascript
const ashley = {
  pronouns: "She" | "Her",
  code: ["Python", "Java", "SQL", "R"],
  technologies: {
    machineLearning: ["Scikit-learn", "TensorFlow"],
    dataScience: ["Pandas", "NumPy", "Matplotlib"],
    dataViz: ["Tableau", "Power BI"],
    cloud: "AWS"
  },
  architecture: "Building end-to-end ML pipelines",
  currentFocus: "Generative AI & Large Language Models",
  funFact: "I'm the innovator behind a patented AI-powered medication dispenser! 💡"
};
#### **Step 2: Create the animation workflow file (`main.yml`)**

This code makes the contribution snake animation work. It must be in a separate file in a specific folder.

1.  In your repository, create a folder named `.github`.
2.  Inside the `.github` folder, create another folder named `workflows`.
3.  Inside the `workflows` folder, create a new file named `main.yml`.
4.  Copy the code below and paste it into the `main.yml` file.

<!-- end list -->

```yml
name: Generate Snake Animation

on:
  schedule:
    - cron: "0 */12 * * *" # Runs every 12 hours
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: Platane/snk@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
