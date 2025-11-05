# Arroword (Collaborative Puzzle App) — Preview

**Arroword** is a real-time, collaborative arrow-word puzzle-solving app for iOS built with SwiftUI and Firebase.  
It brings **live presence collaboration** — similar to real-time document editing — to the world of arrow-word puzzles.

Users can upload a puzzle (from image, PDF, or live scan), invite friends, and solve it together — with each participant’s contributions shown live on the board in real time.

---
## ✨ Key Features

<table>
<tr>
<td width="55%">

<h3>1. <strong>Puzzle Upload & Board Recognition</strong></h3>

Users can start a new shared puzzle group by importing:
<ul>
<li>A <b>photo</b> from the gallery</li>
<li>A <b>PDF document</b> with page selection (as shown to the right)</li>
<li>A <b>live scan</b> using VisionKit</li>
</ul>

Arroword then automatically detects the puzzle’s grid dimensions and initializes a structured puzzle board.

</td>
<td align="right">
<img src="screenshots/loading_new_puzzle_board_small.gif" width="260">
</td>
</tr>
</table>

---

<table>
<tr>
<td width="55%">

<h3>2. <strong>Automatic Puzzle Grid Detection</strong></h3>

After a puzzle file, scan, or image is selected, Arroword automatically detects the <b>grid dimensions</b> and distinguishes <b>definition cells</b> from <b>answer cells</b>.
The puzzle is then converted into a precise, coordinate-indexed grid model.

This enables:
<ul>
<li>Pixel-accurate zoom & pan</li>
<li>Consistent rendering across device sizes</li>
<li>Selectable clue paths with direction toggling</li>
<li>A smooth, touch-native solving experience</li>
</ul>

Any printed puzzle becomes a fully interactive, cell-accurate board — ready for collaborative play.

</td>
<td align="right">
<img src="screenshots/auto_grid_detection_small.gif" width="260">
</td>
</tr>
</table>

---
<table>
<tr>
<td width="55%">

<h3>3. <strong>Real-Time Collaborative Solving</strong></h3>

Multiple users solve the same puzzle together in real time.  
Each participant is assigned a unique color, which clearly communicates:
<ul>
<li>Where they are currently focused</li>
<li>Which cells they have filled</li>
<li>Which clue/path they are working on</li>
</ul>

State is synchronized using Firestore listeners, so all participants see updates instantly — with no manual refresh.

</td>

<td width="45%" align="center">
  <table>
    <tr>
      <td align="center"><img src="screenshots/realtime_board_user_closeup.PNG" width="230"></td>
      <td align="center"><img src="screenshots/realtime_collaboration.PNG" width="230"></td>
    </tr>
  </table>
</td>

</tr>
</table>

---

<table>
<tr>
<td width="55%">

<h3>4. <strong>Lobby View & Collaborative Gamification</strong></h3>

All active puzzles appear in the main lobby as cards, each showing a compact visual summary of the group’s progress:

<ul>
<li>A <b>minimap</b> of the board, with solved cells color-coded by the member who filled them.</li>
<li><b>Member badges</b> above the minimap, ordered by contribution.</li>
<li>A <b>stacked progress bar</b> illustrating both overall completion and each member’s share.</li>
</ul>

This allows players to see progress at a glance and encourages friendly competition, while remaining lightweight through <b>lazy loading</b> and <b>local snapshot caching</b>.

</td>

<td width="45%" align="center">
<img src="screenshots/minimap_board_group.gif" width="260">
</td>

</tr>
</table>

===

<table>
<tr>
<td width="55%">

<h3>5. <strong>Deployment & Beta Testing (TestFlight)</strong></h3>

Arroword has been distributed through **TestFlight** for real-world testing with multiple users (aka my dear family members). 

This enabled iterative refinement of:
<ul>
<li>Interaction flow and control responsiveness</li>
<li>Collaborative sync behavior under real network conditions</li>
<li>Performance on different device sizes and OS versions</li>
</ul>

Using TestFlight ensured the app performs reliably outside the simulator, under real usage patterns.

</td>

<td width="45%" align="center">
  <table>
    <tr>
      <td align="center"><img src="screenshots/testflight_build_info.jpeg" width="260"></td>
    </tr>
  </table>
</td>

</tr>
</table>

---

## 🚧 In Progress: Per-Riddle Chat (Upcoming Feature)

A built-in chat system is currently being developed to allow group members to discuss 
specific clues directly on the puzzle board. The chat opens with a long-press on a cell 
and is scoped to that clue’s context.

This feature is being tested in private TestFlight builds and is undergoing iteration 
based on user feedback and real-world usage.

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


## 👋 Author

**Jonatan Vider**  
iOS & Product Developer  
Tel Aviv, Israel
