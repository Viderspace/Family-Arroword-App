# Arroword (Collaborative Arrow-Word Puzzle App) — Preview

**Arroword** is a real-time, collaborative *arrow-word puzzle* solving app built for iOS using **SwiftUI** and **Firebase**.  
Users can upload a puzzle (from image, PDF, or live camera scan), share it with friends, and solve it together — with each participant’s progress shown live on the board.

This repository provides a **visual overview and product walkthrough** of the app in its current in-development state.  
The full codebase remains private while the app is prepared for release, but this preview demonstrates the core features, UI patterns, system design, and collaborative logic.

---

## 🎥 Demo Video (1 min)

> **Video Link:** *(upload YouTube as Unlisted and replace this line)*  
> `https://youtu.be/PLACEHOLDER`

---

## ✨ Key Features

<table>
<tr>
<td width="55%">

<h3>1. <strong>Puzzle Upload & Board Recognition</strong></h3>

Users can start a new shared puzzle group by importing:
<ul>
<li>A <b>photo</b> from the gallery</li>
<li>A <b>PDF document</b> with page selection  (Like in this instance ---->)</li>
<li>A <b>live scan</b> using VisionKit</li>
</ul>

Arroword then automatically detects the puzzle’s grid dimensions and initializes a structured board.

</td>
<td align="right">
<img src="screenshots/loading_new_puzzle_board_small.gif" width="260">
</td>
</tr>
</table>







<table>
<tr>
<td width="55%">

<h3>2. <strong>Automatic Puzzle Grid Detection</strong></h3>

After a puzzle file, scan, or image is selected, Arroword automatically detects the <b>grid dimensions</b> and distinguishes <b>definition cells</b> from <b>answer (empty) cells</b>. The puzzle is then converted into a precise, coordinate-based grid model.

This enables:
<ul>
<li>Pixel-accurate zoom/pan</li>
<li>Consistent rendering across device sizes</li>
<li>Selectable cell paths with direction toggling</li>
<li>A smooth, touch-native solving experience</li>
</ul>

Any printed puzzle becomes a fully interactive, cell-accurate board—ready for collaborative play.

</td>
<td align="right">
<img src="screenshots/auto_grid_detection_small.gif" width="260">
</td>
</tr>
</table>



<table>
<tr>
<td width="55%">

<h3>3. <strong>Real-Time Collaborative Solving</strong></h3>

Arroword allows multiple users to solve the same puzzle together in real time.  
Each participant is assigned a unique color, which clearly communicates:
<ul>
<li>Where they are currently focused</li>
<li>Which cells they have filled</li>
<li>Which clue/path they are working on</li>
</ul>

State is synchronized through Firestore listeners, so all players see updates instantly with no manual refresh.

</td>

<td width="45%" align="center">
  <table>
    <tr>
      <td align="center"><img src="screenshots/realtime_board_user_closeup.PNG" width="240"></td>
      <td align="center"><img src="screenshots/realtime_collaboration.PNG" width="240"></td>
    </tr>
  </table>
</td>

</tr>
</table>



<table>
<tr>
<td width="55%">

<h3>4. <strong>Contribution Map & Progress Bar</strong></h3>

Each puzzle card in the lobby shows a **minimap** of the board with cells colored by the **member who filled them**.  
Above the minimap: member name badges ordered by contribution.  
Below it: a **stacked progress bar** partitioned by member color, showing the share each person solved.

This provides, at a glance:
<ul>
<li>Group progress & who solved what</li>
<li>Friendly competition that drives engagement</li>
<li>Low bandwidth previews via <b>lazy loading</b> and <b>local snapshot caching</b></li>
<li>Fast updates from Firestore-aggregated cell metadata</li>
</ul>

</td>

<td width="45%" align="center">
  <table>
    <tr>
      <td align="center"><img src="screenshots/minimap_overview_1.PNG" width="240" alt="Minimap with colored contributions"></td>
      <td align="center"><img src="screenshots/minimap_overview_2.PNG" width="240" alt="Member badges and stacked contribution bar"></td>
    </tr>
  </table>
</td>

</tr>
</table>




---

### 3. **Contribution Visualization & Gamification**
The lobby displays a **“minimap” puzzle preview** where each filled cell is shown in the contributor’s color — making progress and collaboration clear at a glance.

Above it, a **color-coded member list** and **stacked bar contribution meter** display how much each user has contributed.

This lightweight gamification drives:
- Friendly competition  
- Engagement  
- Clear progress visibility  

> Demonstrates: Custom drawing in SwiftUI, local snapshot caching, incremental data aggregation, product design thinking.

**Screenshot:**  
`/screenshots/minimap_overview.PNG`

---

### 4. **Smooth Interaction & Puzzle Input**
On tapping a cell:
- The full clue path highlights in the user’s color
- A custom Hebrew keyboard slides up
- Other participants see the highlight live

> Demonstrates: gesture recognition, custom overlay inputs, clue traversal algorithms, bidirectional grid-to-model mapping.

**Screenshot:**  
`/screenshots/focus_and_keyboard.PNG`

---

### 5. **Deployment & Beta Testing (TestFlight)**
Arroword has been distributed privately through **TestFlight** for group testing and iteration.

This ensures real device performance evaluation, UX refinement, and real multi-user stress testing.

**Screenshot:**  
`/screenshots/testflight_builds.PNG`

> Demonstrates: App signing, provisioning, TestFlight deployment, OTA beta distribution.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Language | **Swift**, SwiftUI |
| Realtime backend | **Firebase Firestore** |
| Storage & caching | Firebase Storage, local persistence |
| Document handling | PDFKit, UIKit bridging |
| Scanning / imaging | VisionKit, CoreImage processing |
| Collaboration model | Color-coded shared edit state w/ presence |
| Deployment | TestFlight beta distribution |

---

## 📌 Status

This is an ongoing project in active development.  
The core architecture, workflows, and UI systems are implemented and functioning in production-like conditions with real testers.

The codebase is currently private while the app is prepared for wider release.

If you're evaluating this project in the context of a job application, I’d be happy to **walk through the architecture and selected portions of the code live** in an interview or technical conversation.

---

<p align="center">
  <img src="screenshots/loading_new_puzzle_board_small.gif" alt="Loading a new puzzle board" width="360">
</p>


## 👋 Author

**Jonatan Vider**  
iOS & Product Developer  
Tel Aviv, Israel
