# Kyle-Game:)
# Simple Text-Based Adventure Game

def print_intro():
    print("Welcome to the Adventure Game!")
    print("You find yourself in a mysterious land. Your choices will determine your fate.")
    print("Make the right decisions to survive and find the treasure!")
    print("----------------------------------------")

def choose_path():
    print("You are at a crossroad.")
    print("1. Go left into the dark forest.")
    print("2. Go right toward the mountains.")
    print("3. Go straight ahead to the river.")
    choice = input("What will you do? (1/2/3): ")
    return choice

def forest():
    print("You enter the dark forest. It's eerily quiet.")
    print("You see a glowing object in the distance.")
    print("1. Investigate the glowing object.")
    print("2. Ignore it and continue walking.")
    choice = input("What will you do? (1/2): ")
    if choice == "1":
        print("You found a magical sword! This will help you in your journey.")
        return "sword"
    else:
        print("You continue walking but get lost in the forest. Game Over!")
        return "lost"

def mountains():
    print("You climb the mountains. The air is thin and cold.")
    print("You encounter a troll blocking your path.")
    print("1. Fight the troll.")
    print("2. Try to sneak past it.")
    choice = input("What will you do? (1/2): ")
    if choice == "1":
        print("You bravely fight the troll and defeat it! You continue your journey.")
        return "troll_defeated"
    else:
        print("The troll catches you and you are defeated. Game Over!")
        return "lost"

def river():
    print("You arrive at a fast-flowing river.")
    print("You need to cross it to continue your journey.")
    print("1. Try to swim across.")
    print("2. Look for a bridge.")
    choice = input("What will you do? (1/2): ")
    if choice == "1":
        print("The current is too strong! You are swept away. Game Over!")
        return "lost"
    else:
        print("You find a hidden bridge and safely cross the river.")
        return "river_crossed"

def treasure_room():
    print("You have reached the treasure room!")
    print("Congratulations! You found the hidden treasure and won the game!")
    print("Thank you for playing!")

def game():
    print_intro()
    path = choose_path()

    if path == "1":
        result = forest()
        if result == "lost":
            return
    elif path == "2":
        result = mountains()
        if result == "lost":
            return
    elif path == "3":
        result = river()
        if result == "lost":
            return

    # If the player survives the first choice, they reach the treasure room.
    treasure_room()

# Start the game
game()
