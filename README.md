import time
import random

name = input("Welcome to adventure game! please enter Your Name : ")

print("good luck!, " + name + "\n###Let's Start the Game###")
time.sleep(2)

score = 0


def intro_scene():
    print("As a gold miner, you keep collecting gold that is under ground.")
    time.sleep(2)
    print("However, your new boss turned out to be a very rude , cold person and overworking all the miners there.")
    time.sleep(2)
    print("And he didn't even give you a proper salary that was enough for you and your family.")
    time.sleep(2)
    print("So you couldn't stand there and watch , you decided you will do something....")
    time.sleep(2)


def key_scene():
    global score
    option = random.choice(["shooter", "knife", "chain saws"])

    print("First, you need to make a plan..")
    time.sleep(2)
    print("Choose your plan! please enter 1/2:")
    time.sleep(2)
    plan = input(">")

    if plan == "1":

        score += 3
        trick_one(option)

    else:

        score += 3
        trick_two(option)


def trick_one(option):
    print("You decided that you will put a medicine in your boss's coffee that makes your boss sleep for a while...")
    time.sleep(2)
    print("your friends help you to distract the guards that are standing in front of the boss's office... ")
    time.sleep(2)
    print("your boss successfully drank the coffee and slept..")
    time.sleep(2)
    print("your friends failed to distract the guards by screaming that something big fell down.. ")
    time.sleep(2)
    print("and they entered while you were turning off all the cameras that were placed in the gold mine...")
    time.sleep(2)
    print("will you fight the guards or act like you did nothing?! please enter 1/2 :")
    trick_one_chooses(option)


def trick_one_chooses(option):
    global score
    trick_choose = input(">")
    if trick_choose == "1":

        score += 6
        fight_guards(option)
    else:

        score += 3
        escape_guards()


def fight_guards(option):
    if "chain saws" in option:

        print("the guards were confused at first but realized what's going on and. ")
        time.sleep(2)
        print("started coming towards you.")
        time.sleep(2)
        print("you took out your " + option + " and started fighting the guards..")
        time.sleep(2)
        print("you successfully killed all the guards with the chain saws.")
        time.sleep(2)
        print("you won")
        play_again()

    elif "chain saws " not in option:
        print("you fight the guards using a small knife that wasn't helpful!")
        time.sleep(2)
        print("you are killed.")
        time.sleep(2)
        print("you lost.")
        play_again()


def escape_guards():
    print("you quickly hide under your boss's desk where he is sleeping.... ")
    time.sleep(2)
    print("however, the rest of the guards who are outside come and catch you. ")
    play_again()


def trick_two(option):
    print("You and the other gold miners throw a bomb on a part of the mine...")
    time.sleep(2)
    print("everything is burning, factory smoke and screams...")
    time.sleep(2)
    print("the boss is shocked and is running with his guards to see what's going on ... ")
    time.sleep(2)
    print("you divided the plan on most of the miners because all the people there hated him so they help you..")
    time.sleep(2)
    print("the other miners where beside the burning part of the mine..")
    time.sleep(2)
    print("a miner turned off all the cameras that were placed in the gold mine...")
    time.sleep(2)
    print("you took the others and went to collect as much gold as you all can collect...")
    time.sleep(2)
    print("unluckily, you find your boss in front of you..")
    time.sleep(2)
    print("on his right side are his guards and on the other side are some of the evil miners that are loyal to him..")
    time.sleep(2)
    print("will you fight or act like you are doing nothing ?! please enter 1/2 :")
    trick_two_chooses(option)


def trick_two_chooses(option):
    trick_choose = input(">")
    if trick_choose == "1":
        fight_sec(option)
    else:
        act()


def fight_sec(option):
    if "shooter" in option:
        print("when the guards see you, they are confused at first but realize what's going on and ... ")
        time.sleep(2)
        print("start coming towards you...")
        time.sleep(2)
        print(
            "you and the miners  take out your " + option + " and started fighting the guards and the boss's loyal miners..")
        time.sleep(2)
        print("you successfully killed all the guards with the shooter.")
        print("you won!")
        play_again()
    elif "shooter" not in option:
        print("you all fight the guards using a small knife that wasn't  effective!")
        time.sleep(2)
        print("you and the miners are killed.")
        time.sleep(2)
        print("you lost.")
        play_again()


def act():
    print("you quickly act as if nothing is going on and .... ")
    time.sleep(2)
    print("and the boss believed you all. ")
    time.sleep(2)
    print("good choice!")
    time.sleep(2)
    print("you won!")
    play_again()


def play_again():
    print(f'score : {score}')
    again = input("Would you like to play again? (y/n)").lower()
    if again == "y":
        print("\n\n\n Restarting the game ...\n\n\n")
        time.sleep(2)
        game()
    elif again == "n":
        print("\n\n\nThanks for playing!\n\n\n")
        time.sleep(2)


def game():
    intro_scene()
    key_scene()
    play_again()


if __name__ == '__main__':
    game()
    print(score)
