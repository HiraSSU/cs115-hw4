# cs115-hw4
# How to Run

1. Ensure you have Python 3 installed.
2. Save the `adventure_toolkit.py` file.
3. Open a terminal or command prompt.
4. Navigate to the directory where the file is saved.
5. Run the program with the command: `python3 adventure_toolkit.py`
# 5 test transcripts
## Test 1: Valid Path (Time, Coins, and Adventure Success)

Adventure Toolkit — Chapters 1–3,5
=== Prep Utilities ===
Enter total seconds: 367
H:MM:SS = 0:06:07
Enter copper pieces (cp): 1349
Coins → gp:1  sp:34  cp:9
Enter age: 25
Citizen (y/n): y
Eligible? True

=== Mini-Adventure ===
What is your name, adventurer? shawn
Do you carry a torch? (y/n): y
### DEBUG: name=shawn, has_torch=True

Welcome, shawn. The torches flicker as you enter the ruins…

You reach a fork: left path is windy; right path is silent.
Choose (left/right): right
You spot a hidden alcove with an iron gate.
Enter the 2-digit guard code (3 attempts): 50
Too low.
Enter the 2-digit guard code (2 attempts): 90
Too high.
Enter the 2-digit guard code (1 attempts): 77
Success! The gate opens. Treasure glitters beyond.

## Test 2: Invalid Input Re-prompting (Recursive Input Validation)

Adventure Toolkit — Chapters 1–3,5
=== Prep Utilities ===
Enter total seconds: abc
Please enter a whole number.
Enter total seconds: -5
H:MM:SS = -1:59:55
Enter copper pieces (cp): 1.5
Please enter a whole number.
Enter copper pieces (cp): 100
Coins → gp:0  sp:10  cp:0
Enter age: twenty
Please enter a whole number.
Enter age: 20
Citizen (y/n): maybe
Please enter one of: n, y
Citizen (y/n): Y
Eligible? True

=== Mini-Adventure ===
What is your name, adventurer? shawn
Do you carry a torch? (y/n): y
### DEBUG: name=shawn, has_torch=True

Welcome, shawn. The torches flicker as you enter the ruins…

You reach a fork: left path is windy; right path is silent.
Choose (left/right): left
Your torch reveals markings that guide you safely.
You follow the markings to a sunlit exit. Freedom!

## Test 3: Guard Code Failure Path

Adventure Toolkit — Chapters 1–3,5
=== Prep Utilities ===
Enter total seconds: 200
H:MM:SS = 0:03:20
Enter copper pieces (cp): 200
Coins → gp:0  sp:20  cp:0
Enter age: 25
Citizen (y/n): y
Eligible? True

=== Mini-Adventure ===
What is your name, adventurer? shawn
Do you carry a torch? (y/n): y
### DEBUG: name=shawn, has_torch=True

Welcome, shawn. The torches flicker as you enter the ruins…

You reach a fork: left path is windy; right path is silent.
Choose (left/right): right
You spot a hidden alcove with an iron gate.
Enter the 2-digit guard code (3 attempts): 10
Too low.
Enter the 2-digit guard code (2 attempts): 20
Too low.
Enter the 2-digit guard code (1 attempts): 30
Too low.
Alas, the mechanism locks with a clang.

## Test 4: Eligibility Boundary Values

Adventure Toolkit — Chapters 1–3,5
=== Prep Utilities ===
Enter total seconds: 200
H:MM:SS = 0:03:20
Enter copper pieces (cp): 200
Coins → gp:0  sp:20  cp:0
Enter age: 17
Citizen (y/n): y
Eligible? False

=== Mini-Adventure ===
What is your name, adventurer? shawn
Do you carry a torch? (y/n): n
### DEBUG: name=shawn, has_torch=False

Welcome, shawn. The torches flicker as you enter the ruins…

You reach a fork: left path is windy; right path is silent.
Choose (left/right): left
Darkness hides a pit. You stumble but recover.
Bruised but wiser, you decide to return another day.

## Test 5: Adventure Failure Path (No Torch)

Adventure Toolkit — Chapters 1–3,5
=== Prep Utilities ===
Enter total seconds: 300
H:MM:SS = 0:05:00
Enter copper pieces (cp): 300
Coins → gp:0  sp:30  cp:0
Enter age: 25
Citizen (y/n): y
Eligible? True

=== Mini-Adventure ===
What is your name, adventurer? shawn
Do you carry a torch? (y/n): n
### DEBUG: name=shawn, has_torch=False

Welcome, shawn. The torches flicker as you enter the ruins…

You reach a fork: left path is windy; right path is silent.
Choose (left/right): right
You hear water ahead. The ground is slick.
A shallow stream bars your path; you turn back.

# Contributions section: who did what


# Known issues (if any)
* Negative numbers for seconds or copper pieces are not explicitly validated, though the `ask_int` function ensures they are whole numbers. The output for negative seconds is not human-friendly. This is a minor issue given the prompt's focus on positive integers.
