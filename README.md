# TECHIN 509: Music Composer – Design Doc

In README.md, document your solution idea to build music composer. Use headings, buleet points, code blocks wherever appropriate. Your document should be cleanly formatted and easy to follow.
Think of this problem in a modularized way. The following prompts may guide your thinking:
Input:
What information does the program need to start?
Shall the program request input from users? Make a case for your answer rather than simply give yes or no.
Output:
What does the program produce?
What the generated music might look like, e.g., figures, excel spreadsheet, plain text?
Representation:
How should the program represent notes? Some examples might include letters (C, D, E), numbers (music signal frequencies), strings (C4 quarter note).
How to capture/represent time duration of music notes?
Logic:
How could the program decide what note comes next?
How does the program know when to terminate music generation?
Extensions:
What are blockers for generating longer piece of music?
Note: We do not grade this submission based on correctness. But you should justify your answers.

# **Input**

## * Potentially a login information to be able to retain all of the work of the user and save it. A music composer program would need to start with the user prompting type of _instrument_, _genre_, _era_ to choose from. This would guide the program on the next steps for generating a composition.
    * Button for Generate new piece that would circle back to prompting questions.
   
# **Output**
## * The program will then produce two things:
        * Music notes that are downloadable notes sheet for specific instruments examples:
            * Piano
            * Guitar
            * Trumpet  
          * Generate a play button in the program of the music generated to give idea for what it sounds like
        
# **Representation**

## * The program as mentioned can display notes in the composer. Classical representation of musical notes and letters for musicians in the form of *Music Sheets*. This will be needed for musicians to set up the software on their phone or laptop? 
    * A built in metronome would be helpful to musicians with pacing.  
    * Time duration could of music notes could be marked with a timer mechanism to make sense of the beats per minute or certain pace that is logical for musicians to follow. 
    

# **LOGIC**
## Potential IF statements built in to follow that are plasuible for music note building, following beats, cords, bars etc. 
## Program will terminate based on time duration for the average music genre era and instrument that is appropriate for the piece.


# **Extensions**
## Blockes could be that longer pieces require, memory, and musical structure and not just random note picking. 


###  ASSIGNMENT 02 Melody Representation 

Based on our in-class discussion, how can you store a sequence of notes like C D E F G in Python? Please be specific and give the actual code to represent the example note sequence. Justify your answer carefully!

    Below are some questions to help you starting addressing the problem above:

    If a melody is like a sentence, what would each word be?
    Which Python type keeps items in order (so you know which note comes first, second, third)? Note that this positional information is critical to music.
How to group several melodies together?
Based on your choice of note representation, if you are given a set of melodies to "teach/train" your music composer, how do you prefer the data being stored?

Below are some questions to help you starting addressing the problem above:

If I have a collection of my chosen data type, how can I “flatten” them into one?
Can I start with an empty list all_notes = [] and then add the notes from each melody?
What tool do I know that combines lists?
Suppose you are given a set of melodies, what information would you like to extract to "teach/train" your music composer?

Note: We do not grade this submission based on correctness. In fact, there may not exist a correct answer, rather these answers are your design choices. But you should justify your answers/choices.



## Answers

#Based on our in-class discussion, how can you store a sequence of notes like C D E F G in Python? Please be specific and give the actual code to represent the example note sequence. Justify your answer carefully!

# Organize the sequence of notes in a list 
notes = ["C", "D", "E", "F", "G"]

first = notes[0]          # "C"
notes.append("A")         # ["C","D","E","F","G","A"]
for n in notes: 
    print(n)

This will allow the program to alter the list and change or add notes. 


Below are some questions to help you starting addressing the problem above:

If a melody is like a sentence, what would each word be?
# Each word would be a musical note that is compsoing our melody into a series of words or a sentence. 

Which Python type keeps items in order (so you know which note comes first, second, third)? 
Note that this positional information is critical to music.

# A list will be the most useful here. The order of notes remains the same, their position can be directly pulled and printed.   

print(melody[0])  # First note -> "C"
print(melody[2])  # Third note -> "E"

How to group several melodies together?

#  My first thought would be a dictionary. We can take a list of list and write them under a dictionary. We can then label our melodies or lists under it and print it all together. 

Based on your choice of note representation, if you are given a set of melodies to "teach/train" your music composer, how do you prefer the data being stored?

# I would conitnue with the use of a list of dictionary. 

# Something like this: 
# Use a list of dicts (or JSONL rows), one per melody, with:
#	•	notes: ordered list of events (pitch, duration) (and optionally velocity)
#	•	meta: lightweight metadata (tempo, key, time signature, section, id)
#	•	Keep pitches as strings like "C4" (human-friendly) or MIDI ints (model-friendly)
#	•	Keep durations in beats (e.g., 1.0 = quarter, 0.5 = eighth) or ticks with a PPQ

dataset = [
    {
        "id": "m001",
        "meta": {"title": "Verse A", "tempo": 120, "key": "C", "time_sig": "4/4"},
        # ordered events: (pitch, duration_in_beats)
        "notes": [("C4", 1.0), ("D4", 1.0), ("E4", 1.0), ("F4", 1.0), ("G4", 2.0)]
    },
    {
        "id": "m002",
        "meta": {"title": "Chorus", "tempo": 110, "key": "G", "time_sig": "4/4"},
        "notes": [("G4", 0.5), ("A4", 0.5), ("B4", 1.0), ("A4", 1.0), ("G4", 2.0)]
    }
]


If I have a collection of my chosen data type, how can I “flatten” them into one?
# Goes through each melody in dictionary. 
Code example melodies = [
                            {"id": "m1", "notes": [("C4", 1.0), ("D4", 1.0)]},
                            {"id": "m2", "notes": [("E4", 0.5), ("F4", 0.5), ("G4", 2.0)]}
]
# flat_notes = [note for m in melodies for note in m["notes"]]
# [('C4', 1.0), ('D4', 1.0), ('E4', 0.5), ('F4', 0.5), ('G4', 2.0)]

Can I start with an empty list all_notes = [] and then add the notes from each melody?

# Yes here is how - empty list -> then collecting the notes from the melody in melodies dict. placing them in a big list.

melodies = [
    {"id": "m1", "notes": [("C4", 1.0), ("D4", 1.0)]},
    {"id": "m2", "notes": [("E4", 0.5), ("F4", 0.5), ("G4", 2.0)]}
]

# start with an empty list called all_nots
all_notes = []

# loop through each melody
for melody in melodies:
# loop through each note in the melody
    for note in melody["notes"]:
        all_notes.append(note)   
# add note to the big list

print(all_notes)

What tool do I know that combines lists?

# There is concatenation + sign

Suppose you are given a set of melodies, what information would you like to extract to "teach/train" your music composer?