# Witch Text Based Game
> ### By Alexis Tolliver
> ###### [Back to home page](https://alexisr1990.github.io/Alexis-Tolliver-Portfolio/)


![witch](https://github.com/user-attachments/assets/44342221-f33e-42a3-af30-6bca4e2b254f)




## Summary of Project

This project is a text-based game I created using Python. The wicked witch broke into your house and will put a spell on your entire family which will make them laugh to death unless you defeat her first. In order to defeat the wicked witch you must collect all 6 items from each room before getting to the witch. Once all 6 items are aquired and you get to the witch you can defeat her, but if you get to the witch before collect all 6 items she wins! Below is the Python code I used to creat the game with comments.




### Define new function which includes a greeting, instructions, command list, and inventory list
  
  def welcome_instructions():
      print('Welcome to the Wicked Witch game!')
      print('You are home with your family when the Wicked Witch breaks in! To defeat the witch '
            'before she makes your entire family laugh to death, you must collect all of the items in '
             'each room before encountering the witch!')
      print('Command_list: Go North, Go East, Go South, Go West, Get item')
      print('Inventory List: []')


### Display the welcome_instruction function


  welcome_instructions()



### Create new main function which holds entire game

  
  def main():


  
### A dictionary for the simplified wicked witch text game
### The dictionary links a room to other rooms with
### corresponding directions and items.
    
      rooms = {
          'Mudroom': {'West': 'Basement'},
          'Basement': {'South': 'Kitchen', 'East': 'Mudroom', 'item': 'Bat Blood'},
          'Kitchen': {'West': 'Attic', 'East': 'Sunroom', 'North': 'Basement', 'South': 'Dining Room', 'item': 'Wooden Spoon'},
          'Attic': {'East': 'Kitchen', 'item': 'Magic Wand'},
          'Sunroom': {'North': 'Garage', 'West': 'Kitchen', 'item': 'Wolfsbane'},
          'Garage': {'South': 'Sunroom', 'item': 'Frog Legs'},
          'Dining Room': {'North': 'Kitchen', 'East': 'Living Room', 'item': 'Cauldron'},
          'Living Room': {'West': 'Dining Room', 'item': 'Wicked Witch'}
      }

### Place user in Mudroom
   
      current_room = 'Mudroom'
      next_move = ''
      inventory = []

### As long as the players next move is not the living room, which holds the witch
    
      while next_move != 'Living Room':
          print("\nYou are in", current_room)

### Ask user to input their next move
          
          print('What is your next move?')

### Split players input
          next_move = input().strip().title().split(' ', 1)

### If next move is an option for the current room
        
          if next_move[0] == 'Go' and len(next_move) == 2:
              if next_move[1] in rooms[current_room]:
                  current_room = rooms[current_room][next_move[1]]

### Show player what room they are now in and ask for their next move
                
                  print('Welcome to the', current_room, '!')

### Otherwise tell player they can't go in that direction
            
              else:
                  print('Uh oh! You cannot go that way! Try again!')

### If next room contains item collect it
          
          elif next_move[0] == 'Get' and next_move[1] == 'Item':
              item = rooms[current_room]['item']
              if item not in inventory:
                  inventory.append(rooms[current_room]['item'])
                  print('Nice find! Inventory: ', inventory)

### Otherwise tell player its already in the inventory
            
              else:
                  print('Oops! That item is already in your inventory!')
                  print('Inventory: ', inventory)

          if len(inventory) == 6:
              print('Great job! You collected all of the items now you must find the Wicked Witch!')
        
### If play has all inventory and encounters witch they win
          
          if len(inventory) == 6 and current_room == 'Living Room':
              print('Congratulations! You collected all items and defeated the witch!')
              break

          if len(inventory) <= 5 and current_room == 'Living Room':
              print('Uh oh.. its the Wicked Witch!')
              print('HE HE HE.. I got you now my pretty!!')
              print('Dun dun dun... You lose!')
              break

### Call main function to start game

  main()



##### Resources
Sharpe, G. (2016). Witch. The real and bloody history behind the witches of Halloween. THINKSTOCK. Retrieved July 31, 2024, from https://www.bbc.com/news/uk-scotland-37822022. 
