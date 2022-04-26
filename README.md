# Final-Project
# Explanation - The main difficulty for me came when I tried installing pygame. I spent most of my time studying and learning how to use pygame but when I went to use it non of the functions would work. I then checked the dict to see what my options were and nothing showed up. Somehow my pygame that I downloaded had none of the commands and functions that pygame was supposed to have. This led to me just swithcing to using turtles last minute which is also why I turned it in late. Besides the pygame troubles I truly enjoyed writing the code for the game and figuring out different ways that could add more elements to the game, like trying to figure out how to have the player shoot the guy and if he was late to shooting him he missed.

# Link - https://youtu.be/pkrCb1Uro2c


# Code
import random
import time
import pygame
import turtle
options = [1,2,3]
noptions = [1,2,3,4,5,6]
cpuoptions = [1,2,3,4,5,6,7,8,9,10,11,12]
writer = turtle.Turtle()
cpuguy = turtle.Turtle()
userguy = turtle.Turtle()
userguy.shape("circle")
cpuguy.shape("circle")
bc = turtle.Screen()
bc.bgcolor("green")
writer.hideturtle()
writer.write("Game to 10",move=False, align='center', font=(":Arial", 50, "normal"))
time.sleep(3)
writer.clear()
userguy.penup()
cpuguy.penup()
game = True
while game is True:
    cpuscore = 0
    userscore = 0
    for i in range(21):
        cpuguy.left(90)
        userguy.right(90)
        cpuguy.forward(200)
        userguy.forward(200)
        userguy.right(180)
        userguy.stamp()
        userguy.forward(20)
        userguy.write("2")
        userguy.backward(20)
        cpuguy.right(180)
        cpuguy.stamp()
        cpuguy.forward(20)
        cpuguy.write("2")
        cpuguy.backward(20)
        cpuguy.right(90)
        cpuguy.forward(100)
        cpuguy.left(90)
        cpuguy.stamp()
        cpuguy.forward(20)
        cpuguy.write("1")
        cpuguy.backward(20)
        userguy.right(90)
        userguy.forward(100)
        userguy.left(90)
        userguy.stamp()
        userguy.forward(20)
        userguy.write("3")
        userguy.backward(20)
        cpuguy.left(90)
        cpuguy.forward(200)
        cpuguy.right(90)
        cpuguy.stamp()
        cpuguy.forward(20)
        cpuguy.write("3")
        cpuguy.backward(20)
        userguy.left(90)
        userguy.forward(200)
        userguy.right(90)
        userguy.stamp()
        userguy.forward(20)
        userguy.write("1")
        userguy.backward(20)

        userguy.forward(100)
        userguy.right(90)
        userguy.forward(100)
        userguy.left(90)
        cpuguy.forward(100)
        cpuguy.right(90)
        cpuguy.forward(100)
        cpuguy.left(90)
        
        cpuchoice = random.choice(options)
        while True:
            option = ["1","2","3"]
            writer.write("Choose 1, 2, or 3.",move=False, align='center', font=(":Arial", 50, "normal"))
            userhide = input("Choose 1, 2, or 3.")
            if userhide in option:
                userhide = int(userhide)
                break
            else:
                pass
        userguy.hideturtle()
        userguy.right(180)
        userguy.forward(100)
        if userhide == 1:
            userguy.right(90)
            userguy.forward(100)
            userguy.right(90)
            userguy.showturtle()
        if userhide == 2:
            userguy.right(180)
            userguy.showturtle()
        if userhide == 3:
            userguy.left(90)
            userguy.forward(100)
            userguy.left(90)
            userguy.showturtle()
        if cpuchoice == userhide:
            writer.clear()
            writer.write("They found you!",move=False, align='center', font=(":Arial", 50, "normal"))
            print("They found you!")
            time.sleep(3)
            cpuwait = random.choice(noptions)
            while True:
                cpuoption = ["1","2","3","4","5","6","7","8","9","10","11","12"]
                writer.clear()
                writer.write("How many seconds should you wait to look up?(12 sec max)",move=False, align='center', font=(":Arial", 20, "normal"))
                wait = input("How many seconds should you wait to look up?(12 sec max)")
                if wait in cpuoption:
                    wait = int(wait)
                    break
                else:
                    pass
            first = [1,2]
            second = [3,4]
            third = [5,6]
            fourth = [7,8]
            fifth = [7,10]
            six = [11,12]
            if wait in first:
                wait = 1
            elif wait in second:
                wait = 2
            elif wait in third:
                wait = 3
            elif wait in fourth:
                wait = 4
            elif wait in fifth:
                wait = 5
            elif wait in six:
                wait = 6
            writer.clear()
            time.sleep(wait)
            userguy.forward(10)
            time.sleep(1)
            userguy.backward(10)
            if cpuwait == wait:
                writer.clear()
                writer.write("BOW!",move=False, align='center', font=(":Arial", 50, "normal"))       
                print("BOW!")
                time.sleep(3)
                cpuscore += 1
            else:
                writer.clear()
                writer.write("Close one!",move=False, align='center', font=(":Arial", 50, "normal"))       
                print("Close one!")
                time.sleep(3)
                userscore += 1
        else:
            writer.clear()
            writer.write("Good job, they couldn't find you!",move=False, align='center', font=(":Arial", 50, "normal"))       
            print("Good job, they couldn't find you!")
            time.sleep(3)
            userscore += 1
        writer.clear()

        cpuhide = random.choice(options)
        cpuguy.hideturtle()
        cpuguy.right(180)
        cpuguy.forward(100)
        if cpuhide == 1:
            cpuguy.left(90)
            cpuguy.forward(100)
            cpuguy.left(90)
            cpuguy.showturtle()
        if cpuhide == 2:
            cpuguy.right(180)
            cpuguy.showturtle()
        if cpuhide == 3:
            cpuguy.right(90)
            cpuguy.forward(100)
            cpuguy.right(90)
            cpuguy.showturtle()
        while True:
            option = ["1","2","3"]
            writer.clear()
            writer.write("Where is he? 1, 2, or 3?",move=False, align='center', font=(":Arial", 50, "normal"))       
            userchoice = input("Where is he? 1, 2, or 3?")
            if userchoice in option:
                userchoice = int(userchoice)
                break
            else:
                pass
        if cpuhide == userchoice:
            writer.clear()
            writer.write("You got him! Now try to shoot him!(press enter)",move=False, align='center', font=(":Arial", 30, "normal"))       
            print("You got him! Now try to shoot him!")
            cpusec = random.choice(cpuoptions)
            time.sleep(cpusec)
            running = True
            while running is True:
                cpuguy.forward(10)
                print("Pop Up")
                shoot = "no"
                t1_start = time.perf_counter()    
                shoot = input("press enter")
                t1_stop = time.perf_counter()
                if t1_stop-t1_start <= .5:
                    break
                elif t1_stop-t1_start >= .5:
                    shoot = "no"
                    break
                cpuguy.backward(10)
            if shoot == "":
                writer.clear()
                writer.write("You got him!",move=False, align='center', font=(":Arial", 50, "normal"))       
                print("You got him!")
                time.sleep(3)
                userscore += 1
            else:
                writer.clear()
                writer.write("You missed him!",move=False, align='center', font=(":Arial", 50, "normal"))       
                print("you missed him")
                time.sleep(3)
                cpuscore += 1
    
        else:
            writer.clear()
            writer.write("He wasn't there.",move=False, align='center', font=(":Arial", 50, "normal"))       
            print("He wasn't there.")
            time.sleep(3)
            cpuscore += 1
        writer.clear()    
        #writer.write("Adversary:",cpuscore, "You:",userscore,move=False, align='center', font=(":Arial", 50, "normal"))       
        if cpuscore == 1:
            writer.write("Adversary: 1",move=False, align='center', font=(":Arial", 50, "normal"))       
            time.sleep(2)
            writer.clear()
        elif cpuscore == 2:
            writer.write("Adversary: 2",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        elif cpuscore == 3:
            writer.write("Adversary: 3",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        elif cpuscore == 4:
            writer.write("Adversary: 4",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        elif cpuscore == 5:
            writer.write("Adversary: 5",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        elif cpuscore == 6:
            writer.write("Adversary: 6",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        elif cpuscore == 7:
            writer.write("Adversary: 7",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        elif cpuscore == 8:
            writer.write("Adversary: 8",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        elif cpuscore == 9:
            writer.write("Adversary: 9",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        else:
            pass
        if userscore == 1:
            writer.write("You: 1",move=False, align='center', font=(":Arial", 50, "normal"))       
            time.sleep(2)
            writer.clear()
        elif userscore == 2:
            writer.write("You: 2",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        elif userscore == 3:
            writer.write("You: 3",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        elif userscore == 4:
            writer.write("You: 4",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        elif userscore == 5:
            writer.write("You: 5",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        elif userscore == 6:
            writer.write("You: 6",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        elif userscore == 7:
            writer.write("You: 7",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        elif userscore == 8:
            writer.write("You: 8",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        elif userscore == 9:
            writer.write("You: 9",move=False, align='center', font=(":Arial", 50, "normal"))
            time.sleep(2)
            writer.clear()
        else:
            pass
        print("Adversary:",cpuscore, "You:",userscore)
        userguy.goto(0,0)
        cpuguy.goto(0,0)
        userguy.right(90)
        cpuguy.left(90)
        if cpuscore >= 10:
            writer.clear()
            writer.write("Adversary Wins!",move=False, align='center', font=(":Arial", 50, "normal"))       
            print("Adversary Wins!")
            time.sleep(3)
            break
        elif userscore >= 10:
            writer.clear()
            writer.write("Winner!",move=False, align='center', font=(":Arial", 50, "normal"))       
            print("Winner!")
            time.sleep(3)
            break
        else:
            pass
    if cpuscore or userscore == 10:
        game = False
