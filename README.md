
 correct answer for each level
RightAnswer1=["fly","boat","run","is"]
RightAnswer2=["office","choose","codes","casual"]
RightAnswer3=["cold","temperatures","low","horse"]

 there are 4 blanks on each level
blanks=["___1___","___2___","___3___","___4___"]

 3 levels and each level contains 4 blanks to fill in .
easy ='''We can't ___1___ like birds so we invented the plane.
        We can't swim like fish so we invented the ___2___.
        We can't ___3___ like cheetahs so we invented the car.
        Man ___4___ good at inventions but we can't beat the beasts at
        everything.'''
medium= '''for many ___1___ workers,however,it is more difficult to
 ___2___ clothes for work .they don't wear uniforms to the office .
 Also,many employers are changing their dress ___3___. they are allowing their
 employees to wear ___4___ clothes to work.'''
hard='''If you are tired of the ___1___ winter, think about the residents of
  a Russian town who say that they live in the coldest town on Earth.
  Their town is called Oymyakon and it lies deep in Siberia.
  The ___2___ there very often drop to minus 60.
  These local people say that these ___3___ temperatures sometimes last for ten
  days in a row.There is another amazing thing in their town. It is a horse
  that survives in these low temperatures.
  The ___4___ is small but perfectly formed for cold winters.'''

start game and the user choose level what they want then the level is run the funcation .
def start():
 print ('welcome to the star game')
 level= raw_input("choose your game level ? 1-easy,2-medium,3-hard") .lower()
 if level=="easy" :
             rune(easy)
 if level=="medium":
             runm(medium)
 if level=="hard" :
             runh(hard)
 else: return level


def rune(pragrapheasy):
    """
     start function used another function called (checkinput)to compare
     between the right answer and the input word. After that, if the procedure finished it will
     tranfer to another level by the procedure.
     input: pragrapheasy
     output: print easy
     print this sentence ("Congratulation , you are qualified for the next pragraph")
     run runm(medium) funcation
    """
    print checkinput(pragrapheasy,RightAnswer1,blanks)
    print("Congratulation , you are qualified for the next pragraph")
    runm(medium)

def runm(pragraphmedium):
    """
     start function used another function called (checkinput)to compare
     between the right answer and the input word. After that, if the procedure finished it will
     tranfer to another level by the procedure.
     input:pragraphmedium
     output:print medium
     print this sentence ("Congratulation , you are qualified for the next pragraph")
     run runh(hard) funcation
    """
    print checkinput(pragraphmedium,RightAnswer2,blanks)
    print("Congratulation , you are qualified for the next pragraph")
    runh(hard)

def runh(pragraphhard):
    """
     start function used another function called (checkinput)to compare
     between the right answer and the input word. After that,  the procedure will be finished .
     input:pragraphhard
     output:print hard
     print this sentence ("the end")
    """
    print checkinput(pragraphhard,RightAnswer3,blanks)
    print ("the end")


def checkinput(pragraph,RightAnswer,blanks):

    """
     the if function will check if the input word is Right then the word will be
     saved and return to end the blank
     then return to previous procedure(rune(pragrapheasy) OR runm(pragraphmedium)
     OR runh(pragraphhard)).
     input: pragraph,RightAnswer,blanks
     output: print pragraph or print wrong answer
    """
    blank_count=0
    print pragraph
    while blank_count<len(blanks):
     word_input=raw_input("fill in the blanks").lower()
     if word_input==RightAnswer[blank_count]:
       pragraph= pragraph.replace(blanks[blank_count], RightAnswer[blank_count])
       print pragraph
       blank_count=blank_count+1
     else:
        print"wrong answer"
start()
