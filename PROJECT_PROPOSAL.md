# COMPLE — Project Proposal

**Team 1**  
**GitHub Repository:** [vanzele/COMPLE_Project](https://github.com/vanzele/COMPLE_Project)

## Team Members

| Full Name (Last, First) | Student ID | UML Email |
| --- | --- | --- |
| Essien, Vanzel | 02092238 | Vanzel_Essien@student.uml.edu |
| Pham, Jaclyn | 02081515 | Jaclyn_Pham@student.uml.edu |
| Danquah, Jayden | 02090062 | Jayden_Danquah@student.uml.edu |
| Sharwood, Rowan | 02090573 | Rowan_Sharwood@student.uml.edu |

## Mission Statement

The goal for the user is to take the starting word and input valid words that are **one letter different**, slowly changing the word to reach the target word.

**Example:** `CAME → CAMP → COMP`

The game encourages players to expand their vocabulary while developing logical thinking and problem-solving abilities.

## Project Information and Background

Our project takes an educational spin on the web-based word game *Poople*, where players transform a starting word into a target word by changing one letter at a time. Our Android application will offer three difficulty levels: **Easy (CODE)**, **Medium (COMP)**, and **Hard (BOOL)**, each with a set of predetermined starting words. The game is designed for players who enjoy word puzzles and want to challenge their vocabulary and problem-solving skills.

Players will be able to:

- Select a difficulty level and receive a random starting word.
- Transform the starting word into the target word by changing one letter at a time, using only valid four-letter words.
- Make unlimited guesses, including revisiting previous words, with each valid transformation counting as a guess.
- View their total guesses compared to the minimum possible guesses upon completing the puzzle.

## Proposed App Design and Architecture

### Screen Depictions

Our application will consist of six main screens:

1. **Main Menu:** Allows players to start a new game, view statistics, or access instructions.
2. **Difficulty Selection:** Allows players to select Easy (`CODE`), Medium (`COMP`), or Hard (`BOOL`). Each difficulty has a predetermined list of possible starting words.
3. **Game Screen:** Displays the starting word, target word, current word, and guess counter. Players enter four-letter words, changing exactly one letter at a time. Only valid transformations count as guesses, and players can revisit previously used words.
4. **Results Screen:** Displays the player's total guesses compared to the minimum possible guesses, calculated using the Breadth-First Search (BFS) algorithm.
5. **Statistics Screen:** Displays previous results and personal best scores for each difficulty.
6. **Help Screen:** Displays instructions on how to play the game.

### Architecture

The application will use a single `MainActivity` with multiple Fragments representing the different screens. Android's Navigation Component will handle screen transitions, while Safe Args will pass information such as the selected difficulty and puzzle results between Fragments. View Binding will connect UI elements to Java code, and a ViewModel will manage gameplay state, including the current word, guess count, and word history.

### Game Logic

The game will randomly select a starting word from a predefined list based on the chosen difficulty. Player submissions will be checked against a local dictionary to ensure they are valid four-letter words that differ from the current word by exactly one letter. BFS will be used to determine the shortest possible solution for each puzzle.

### Data Persistence

The application will save completed puzzles, personal best scores, and unfinished game progress so players can resume their games after closing the app. A local storage system, such as Room or SharedPreferences, will be used. ViewModel and saved instance state (`Bundle`) will help preserve relevant gameplay information during configuration changes, such as screen rotation.

### External APIs

**N/A.** The application will use a locally stored word dictionary and predefined starting words, so no external APIs are required.

## Proposed Tasks

### Task 1 — User Interface, Navigation, and Data Persistence

Develop the application's main screens, including the Main Menu, Difficulty Selection, Game, Results, Instructions, and Statistics screens. Implement navigation between screens and display gameplay information and results. Add local data persistence to save completed games, personal best scores, and unfinished game progress.

- **Deliverables:** Functional Android interface, screen navigation, results comparison, statistics tracking, and saved game data.
- **Testing:** Verify that all screens function correctly, navigation passes the appropriate information, and saved data is restored after closing and reopening the application.

### Task 2 — Game Logic and Word Validation

Implement the core gameplay mechanics, including the three difficulty levels (Easy, Medium, and Hard), random selection of predetermined starting words, and word validation. Players will transform words by changing exactly one letter per guess, with only valid transformations increasing the guess counter. A Breadth-First Search (BFS) algorithm will determine the minimum possible guesses for each puzzle.

- **Deliverables:** Functional word validation, difficulty-based puzzle selection, guess tracking, and shortest-path calculation.
- **Testing:** Verify that invalid words or transformations do not increase the guess count, previously used words are accepted, and BFS correctly calculates the minimum number of guesses.

### Task 3 — Integration and Testing

Integrate the gameplay logic with the user interface and test the completed application on an Android emulator or physical device. Test all three difficulty levels, word validation, guess counting, navigation, data persistence, and state recovery during screen rotation. Fix any identified bugs and gather feedback from classmates.

- **Deliverables:** A fully integrated, functional Android application with verified gameplay features.
- **Testing:** Complete multiple puzzles across all difficulties, intentionally submit invalid guesses, revisit previous words, restart the app, and rotate the device to confirm that gameplay and saved data behave correctly.

### Extra Task (Optional) — Room Database Statistics Tracking

Implement Room Database to store detailed statistics from completed games, including difficulty level, starting word, number of guesses, minimum possible guesses, and completion history. Players will be able to view their previous results and track improvements over time.

- **Deliverables:** A Room database integrated with the Statistics screen to display saved game history and performance statistics.
- **Testing:** Complete multiple games across different difficulties, verify that records are stored correctly, and confirm that statistics remain available after closing and reopening the application.

## Possible Learning Efforts

- **Local Room Database:** Learn to use Android's Room persistence library to store completed puzzles, guess counts, personal best scores, and game history locally. We will review documentation and practice saving and loading records so players can track their progress across sessions.
- **Breadth-First Search (BFS):** Learn how to apply BFS to a word transformation graph to determine the shortest possible path between a starting word and its target. We will implement the algorithm in Java to ensure the minimum guess count is calculated correctly.

## Proposed Timeline to Complete Tasks

| Week | Dates (2026) | Planned Work | Team Members |
| --- | --- | --- | --- |
| **Week 1** | Nov 8–14 | Come up with an eligible word database and arrange words into CODE, COMP, and BOOL difficulty levels. | Vanzel, Jayden, Jaclyn, Rowan |
| **Week 2** | Nov 15–21 | Create and implement navigation logic between MainActivity and Fragments. | Jaclyn, Jayden, Rowan |
| **Week 3** | Nov 22–28 | Complete all UI screens and implement word validation and BFS. | Vanzel, Jayden, Jaclyn, Rowan |
| **Week 4** | Nov 29–Dec 5 | Connect game logic to the UI, implement guess tracking, and integrate all features. | Vanzel, Jayden, Jaclyn, Rowan |
| **Week 5** | Dec 6–10 | Complete testing, create the presentation, and submit the final project. | Vanzel, Rowan (testing); all members (presentation) |

## Plan for Collaborative Work

### Task Assignments

| Task | Assigned Team Members |
| --- | --- |
| **Task 1 — User Interface, Navigation, and Data Persistence** | Jaclyn, Jayden, Rowan |
| **Task 2 — Game Logic and Word Validation** | Vanzel, Jayden, Jaclyn, Rowan |
| **Task 3 — Integration and Testing** | Vanzel, Rowan |
| **Extra Task (Optional) — Room Database Statistics Tracking** | TBD |

### Meetings and Communication

We will meet **weekly or biweekly**, either on Discord or in person. We will all be involved in the development process, using each other as resources and helping as needed. All development issues will be brought up in weekly or biweekly meetings and handled accordingly.

### GitHub Collaboration

Our shared GitHub repository will manage development and track individual contributions. Each member will work on their assigned tasks using separate branches, then submit pull requests to merge completed features into the main branch. We will review changes, resolve merge conflicts, and communicate through Discord to ensure all components work together.

## Other

N/A.
