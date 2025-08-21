# Halo, saya Fathur Kazama! 👋
Saya seorang Web Developer & Cyber Security Enthusiast.

### Keahlian Saya
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

### Statistik GitHub Saya
![Fathur's GitHub Stats](https://github-readme-stats.vercel.app/api?username=fathurkazama&show_icons=true&theme=vue-dark)

### Mari Terhubung
-   Email: `fathur@fathurkazama.id`
-   Website: https://my.fathurkazama.id
-   Facebook: https://facebook.com/fathur.yt.7

### 💡 Quote of the Day
<!--START_QUOTE-->

<!--END_QUOTE-->

- name: Update README.md
  run: |
    START_MARKER="<!--START_QUOTE-->"
    END_MARKER="<!--END_QUOTE-->"
    README_FILE="README.md"

    QUOTE="${{ steps.get_quote.outputs.quote }}"

    # Pastikan quote nggak kosong
    if [ -z "$QUOTE" ]; then
      echo "No quote fetched!"
      exit 1
    fi

    # Gunakan awk biar lebih aman daripada sed
    awk -v start="$START_MARKER" -v end="$END_MARKER" -v q="$QUOTE" '
      $0 ~ start {print; print q; f=1; next}
      $0 ~ end {print; f=0; next}
      !f {print}
    ' "$README_FILE" > tmp && mv tmp "$README_FILE"

