# cs115-hw4
## How to Run

1. Ensure you have Python 3 installed.
2. Save the `adventure_toolkit.py` file.
3. Open a terminal or command prompt.
4. Navigate to the directory where the file is saved.
5. Run the program with the command: `python3 adventure_toolkit.py`
## 5 test transcripts
### Test 1: Valid Path (Time, Coins, and Adventure Success)

Adventure Toolkit — Chapters 1–3,5
=== Prep Utilities ===
Enter total seconds: 367
H:MM:SS = 0:06:07
Enter copper pieces (cp): 1349
Coins → gp:1 sp:34 cp:9
Enter age: 25
Citizen (y/n): y
Eligible? True

=== Mini-Adventure ===
What is your name, adventurer? Anya
Do you carry a torch? (y/n): y

Welcome, Anya. The torches flicker as you enter the ruins…
You reach a fork: the left path is windy; the right path is silent.
Choose (left/right): right
You spot a hidden alcove with an iron gate, shimmering with a faint light.
Enter the 2-digit guard code (3 attempts): 50
Too low.
Enter the 2-digit guard code (2 attempts): 90
Too high.
Enter the 2-digit guard code (1 attempts): 77
Success! The gate opens...
Treasure glitters beyond! You have found the lost wealth of the ancients.


### Test 2: Invalid Input Re-prompting (Recursive Input Validation)

Adventure Toolkit — Chapters 1–3,5
=== Prep Utilities ===
Enter total seconds: abc
Please enter a whole number.
Enter total seconds: -5
H:MM:SS = 0:-5:00
Enter copper pieces (cp): 1.5
Please enter a whole number.
Enter copper pieces (cp): 100
Coins → gp:0 sp:10 cp:0
Enter age: twenty
Please enter a whole number.
Enter age: 20
Citizen (y/n): maybe
Please enter one of: y, n
Citizen (y/n): Y
Eligible? True


### Test 3: Guard Code Failure Path

... (Prep Utilities omitted for brevity)
=== Mini-Adventure ===
What is your name, adventurer? Gorok
Do you carry a torch? (y/n): y

Welcome, Gorok. The torches flicker as you enter the ruins…
You reach a fork: the left path is windy; the right path is silent.
Choose (left/right): right
You spot a hidden alcove with an iron gate, shimmering with a faint light.
Enter the 2-digit guard code (3 attempts): 10
Too low.
Enter the 2-digit guard code (2 attempts): 20
Too low.
Enter the 2-digit guard code (1 attempts): 30
Too low.
No attempts left. The guard code remains a mystery.
Alas, the mechanism locks with a clang, sealing your fate.


### Test 4: Eligibility Boundary Values

... (Prep Utilities)
Enter age: 17
Citizen (y/n): y
Eligible? False
Enter age: 18
Citizen (y/n): n
Eligible? False
Enter age: 18
Citizen (y/n): y
Eligible? True


### Test 5: Adventure Failure Path (No Torch)

... (Prep Utilities omitted for brevity)
=== Mini-Adventure ===
What is your name, adventurer? Elara
Do you carry a torch? (y/n): n

Welcome, Elara. The torches flicker as you enter the ruins…
You reach a fork: the left path is windy; the right path is silent.
Choose (left/right): right
You hear the sound of dripping water ahead. The ground becomes slick and you decide to turn back.
The path is impassable. You retreat, deciding the risk is too great.


## Contributions section: who did what

## Known issues (if any)
* Negative numbers for seconds or copper pieces are not explicitly validated, though the `ask_int` function ensures they are whole numbers. The output for negative seconds is not human-friendly. This is a minor issue given the prompt's focus on positive integers.
