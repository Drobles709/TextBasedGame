# TextBasedGame
#introduction
introduction = ['Dragon Text Adventure Game']
for text in introduction:
    print(text)
print("Collect 6 items to win the game, or be killed by the intruder.")
print("Move commands: go South, go North, go East, go West, or exit")
print("Add to Inventory: get 'item name'")



#A dictionary for the simplified dragon text game
#The dictionary links a room to other rooms. From typing import List

rooms = {
    'Bedroom1': {'East': 'Bedroom2', 'item': 'baseball bat'},
    'Bedroom2': {'East': 'Balcony', 'item': 'baseball bat'},
    'Balcony': {'West': 'Bedroom', 'item': 'shoes'},
    'Bedroom': {'South': 'Living room', 'item': 'item retrieved bedroom2'},
    'Living room': {'West': 'Attic', 'item': 'alarm'},
    'Attic': {'East': 'Living area', 'item': 'item retrieved Living room'},
    'Living area': {'East': 'Garage', 'item': 'jacket'},
    'Garage': {'North': 'Basement', 'item': 'shield'},
    'Basement': {'South': 'garage', 'item': 'item retrieved Garage'},
    'garage': {'West': 'Living Room', 'item': 'item retrieved Living Room'},
    'Living Room': {'South': 'Kitchen', 'item': 'nutrition bar'},
    'Kitchen': {'West': 'Backyard', 'item': 'light'},
    'Dining room': {'Intruder'},

}



#player current room
current_room = 'Bedroom1'
list = []





while current_room != 'exit':

    print('You are in the', current_room)
    list.append((rooms[current_room]['item']))
    len(list)
    if len(list)== 12:
        print('Congratulation you have collected all the items')
    elif len(list) != 8:
        print('You did not get all the items')
    print(list)

    print('-------------------------------------')
    move = input('Enter your move:')
    move_list = move.split()
    if move_list == 'villan':
        break
        print('You have lost the game')

        if not move_list[0] != 'exit':
        print('Thanks for playing the game.')

    elif move_list[1] == 'North' and 'North' in rooms[current_room]:
        current_room = rooms[current_room]['North']
    elif move_list[1] == 'South' and 'South' in rooms[current_room]:
        current_room = rooms[current_room]['South']
    elif move_list[1] == 'East' and 'East' in rooms[current_room]:
        current_room = rooms[current_room]['East']
    elif move_list[1] == 'West' and 'West' in rooms[current_room]:
        current_room = rooms[current_room]['West']
    else:
        print('Invalid move')

    
