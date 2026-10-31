# Core Loop

The player plays one Coffee Making mini-game round, which takes 3 minutes. They win or lose, see how the [[Cultural Awareness Rate]] (CAR) changes, read a fun fact about Lipa’s coffee, and earn progress toward [[Puzzle Pieces|puzzle pieces]], stories, and cafe customization. Then the loop repeats.

![[gamedev.jpg]]

- **Play**: You get a coffee order and tap the right ingredients at the right moment. It’s quick and easy to pick up, with no gaming experience needed. Tuklas watches along and reacts with its facial expressions as you tap.
- **Win or Lose:** You find out right away how the round went. A win feels rewarding, and a loss is a small setback, not a game over. Either way, you can try again immediately, so the pressure stays low.
- **CAR goes up (win):** Your [[Cultural Awareness Rate]] climbs, and you earn points. You can see Lipa’s world improve, which makes your effort feel meaningful. The next round may get a bit harder to keep things interesting.
- **CAR goes down (lose):** The [[Cultural Awareness Rate]] drops a little. The next round may feel easier, so you can recover. Lipa’s world may look a bit more worn down, which gives you a reason to try again.
- **Reward (fun fact):** After every round, a short fun fact about Lipa’s coffee heritage pops up. It’s small and easy to read, so learning feels like a little prize for playing, not a lesson.
- **Progress ([[Puzzle Pieces|puzzle pieces]], stories, cafe customization):** Every 5 rounds, you earn a puzzle piece that unlocks a short story about a character from Lipa. As your points add up, you can spend them to customize your cafe. You always have something to look forward to, which keeps you playing.
- **Back to Play:** The game starts again. Rounds are short, so it’s easy to keep going, and each round feels a little different because the difficulty adjusts to how you’re doing.

# Controls & Player Actions

**Tuklas-Eh!** uses a fixed 2D camera view in landscape orientation, designed specifically for mobile devices. There is no free camera movement, as players navigate through different screens, such as the map, the Coffee Making mini-game, and the results screen. The game does not involve character or avatar movement since it is entirely touch-based and played in rounds. Instead, players rely on their timing accuracy when tapping the correct coffee ingredients, which serves as the main skill being tested throughout the game.

| <center>Input</center>                     | <center>Action</center>         | <center>Context / Notes</center>                                                                |
| ------------------------------------------ | ------------------------------- | ----------------------------------------------------------------------------------------------- |
| Tap "Play"                                 | Start a round                   | From the Map.                                                                                   |
| Tap ingredient (timed)                     | Prepare the coffee order        | Tap the right ingredient at the right moment. Better timing means better customer satisfaction. |
| Tap Pause icon                             | Pause game                      | Opens the Paused Game screen with resume and exit.                                              |
| Tap fun fact box                           | Dismiss and continue            | Appears after every round.                                                                      |
| Tap [[Puzzle Pieces\|puzzle piece]] / story | Read character story            | Appears when a puzzle piece is earned (every 5 rounds).                                         |
| Tap menu icons                             | Open Achievements, and Settings | View achievements. In Settings, change the volume or log out.                                   |
| Sign up / Log in fields                    | Create or access account        | Needed for progress sync with the database.                                                     |

## Game Rules & Logic

**Win Condition:**
- Per round: Complete the coffee order accurately within the timing window.
- Per session or long term: There is no single end boss. The player "wins" by raising the [[Cultural Awareness Rate|CAR]] toward 75% or higher, moving the world to the restored state, and unlocking all stages, [[puzzle pieces]], and stories.

**Fail Condition:**
- Per round: Missing the timing or tapping the wrong ingredient, which counts as a loss.
- Per session: None. There is no game-over or hard reset, which keeps the experience low-pressure.

**Failure Penalty:**
- The [[Cultural Awareness Rate|CAR]] drops, and with it the world can slide toward the degraded state.
- The next round's difficulty adjusts, and a loss streak (three in a row) changes [[Tuklas]]'s reactions.
- Points, [[puzzle pieces]], stories, and achievements already earned are not lost.

**Save & Persistence System:**
- Saving happens automatically, so no manual save files are needed.
- Progress is tied to the player's account, so it persists across sessions and devices.
- The game fails gracefully and recovers its state after a poor connection or interruption. 

