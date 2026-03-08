<h1 align="center">👾 Flashed Invaders Tracker</h1>
<h3 align="center">A personal, automated database tracking all the Space Invaders street art I have successfully "flashed".</h3>

---

<br/>

<p align="center">
  <a href="https://github.com/GestaltCaius/flashed-invaders/blob/main/flashed-invaders.json">
    <img alt="Flashed Invaders Count" src="https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/GestaltCaius/flashed-invaders/main/badge.json">
  </a>
  <a href="https://github.com/GestaltCaius/flashed-invaders/actions/workflows/import_new_invaders.yaml">
    <img alt="GitHub Actions Workflow Status" src="https://github.com/GestaltCaius/flashed-invaders/actions/workflows/import_new_invaders.yaml/badge.svg">
  </a>
</p>

<br/>

---

## ⚙️ How it works

This repository is fully automated using GitHub Actions. I never have to edit the main JSON database manually.

**To add new invaders:**
1. Drop a simple text file (e.g., `paris_trip.txt`) into the `inputs/` folder.
2. Write one invader ID per line (e.g., `PA_1485`).
3. Commit and push to the `main` branch.

**The automated workflow will then:**
- Parse the text files and clean up any blank lines or invisible spaces.
- Merge the new IDs into the master [`flashed-invaders.json`](flashed-invaders.json) database (ignoring duplicates).
- Keep a timestamped history of the import in the `changelog/` folder.
- Delete the processed `.txt` file to keep the repository clean.
- Dynamically update the total counter badge at the top of this README.

## 📂 Structure

- 💾 **[`flashed-invaders.json`](flashed-invaders.json)**: The master list containing all unique flashed invaders.
- 📥 **`inputs/`**: The drop-zone folder for new text files.
- 🗄️ **`changelog/`**: Automatically generated JSON backups of every individual import.