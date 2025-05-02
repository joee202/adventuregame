import random
import time
def main():
    while True:
        Mon = ["GIANT", "WITCH", "DRAGON", "GIANT SPIDER"]
        Monster = random.choice(Mon) #random monsters here
        fru = ("glowing berry","golden apple","enchanted kiwi","golden carrot") #random fruits for later
        fruit = random.choice(fru)
        score = 0
        print("Welcome to the adventure game!")
        time.sleep(2)
        print(f"You are a brave warrior on a quest to defeat a {Monster}.")
        time.sleep(2)
        print("You are in a big field where you find trees and nature all around you.")
        time.sleep(2)
        print(f"They say that a {Monster} is roaming around in this field.")
        time.sleep(2)
        print(f"You have to find the {Monster} and kill it.")
        time.sleep(2) #expalanation about the area you are in.
        print("There are 3 paths in front of you.")
        time.sleep(2)
        print("1. Left where you can see a deep cave.")
        time.sleep(2)
        print("2. Right where you can see a giant tree to climb.")
        time.sleep(2)
        print("3. Straight where you can discover more about the field.")
        time.sleep(2)
        path = input("Choose your path (1, 2, or 3): ")#first decision to make
        eat = "no" # to set eat to default when going to path 2
        if path == "1":
            print("You have chosen the left path.")
            time.sleep(2)
            print("You are in a cave and you can see a treasure chest.")
            time.sleep(2)
            print("You open the chest and find an enchanted sword and an enchanted bow.")
            time.sleep(2)
            print("1. Enchanted sword")
            print("2. Enchanted bow")  # second choice
            choice = "" #necessary for th while loop
            while choice not in ["1", "2"]:
                choice = input("Choose your weapon: ")
                if choice == "1":
                    weapon = "an enchanted sword"
                    print("You have chosen the enchanted sword.")
                    score += 1
                    print("Your score is now:", score)
                    #if condition for choosing the sword
                elif choice == "2":
                    weapon = "an enchanted bow"
                    print("You have chosen the enchanted bow.")
                    score += 1
                    print("Your score is now:", score)
                    #if condition for choosing the bow
                else:
                    print("ERROR! Choose between 1 and 2.")
                    #for choosing anything but 1 and 2
        elif path == "2":
            print("You have chosen the right path.")
            time.sleep(2)
            print("You are at the top of the tree and you can see the whole field.")
            time.sleep(2)
            print(f"You can see the {Monster} in the distance.")
            time.sleep(2) #path 2 code
            attack = input(f"Do you want to attack the {Monster} and trust your weapon? (yes/no): ").lower()
            #choose to attack or not
            if attack == "yes":
                print("You have chosen to attack the monster.")
                time.sleep(2) #if condition for anything you had earlier that could defeat the monster
                if "1" or "2" in weapon or eat == "yes":
                    print(f"You attack the {Monster} with your powerful abilities.")
                    time.sleep(2)
                    print(f"You killed the {Monster} in two hits!")
                    time.sleep(2)
                    print("You Won!")
                    score += 1
                else: #if condition if you didn't have anything to kill the monster
                    print(f"You attack the {Monster} with your weak weapon.")
                    time.sleep(2)
                    print("You lost your weapon and you are dead.")
                    score -= 1
                    print("Game Over.")
                print("Your score is now:", score)
                restart = input("Do you want to start again? (yes or no): ").lower()
                if restart != "yes": #play again text
                    print("Thanks for playing.")
                    break
                else:
                    print("Game Restarted.\n")
                    time.sleep(2)
                    continue
            else: #else for not going and choosing to kill the moster
                print("You chose not to attack the monster.")
                score += 1
                print("Your score is now:", score)
        elif path == "3": #path 3 condition
            print("You chose the straight path.")
            time.sleep(2)
            print(f"You find a peaceful field and a {fruit}.")
            time.sleep(2)
            eat = input(f"Do you want to eat the {fruit}? (yes/no): ").lower()
            if eat == "yes":
                print(f"You chose to eat the {fruit}.")
                time.sleep(2)
                print("You feel stronger and more powerful.")
                score += 1
            else:
                print(f"You chose not to eat the {fruit}.")
                time.sleep(2)
                print("You feel weak and tired due to all the movement.")
                score -= 1 #if condition for not choosing 
            print("Your score is now:", score)
            time.sleep(2)
            print("Then you find a bridge where you can spot the monster after a while.")
            time.sleep(2)
            print("The bridge feels weak.")
            print("1. Cross the bridge.")
            print("2. Go back to the field.")
            choice = input("Choose your action (1 or 2): ")
            if choice == "1": # another choice
                print("You chose to cross the bridge.")
                time.sleep(2)
                print("The bridge collapses and you fall into the river.")
                time.sleep(2)
                print("You are dead.")
                score -= 1
                print("Your score is now:", score)
                print("Game Over.")
                restart = input("Do you want to start again? (yes or no): ").lower()
                if restart != "yes":
                    print("Thanks for playing.")
                    break
                else: #play again question
                    print("Game Restarted.\n")
                    time.sleep(2)
                    continue
            elif choice == "2":
                print("You chose to go back to the field.")
                score += 1
                print("Your score is now:", score)
            else:
                print("Invalid choice. Please choose 1 or 2.")
        else:
            print("Invalid path. Please choose 1, 2, or 3.")

main()
