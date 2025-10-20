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
