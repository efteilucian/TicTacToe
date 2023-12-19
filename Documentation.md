1.Introduction 
This documentation provides information about a simple TicTacToe game implemented in Java using the Swing library. 
It allows two players to take turns marking cells on a 3x3 grid with 'X' and 'O' symbols. 
The game announces the winner when a player successfully forms a line horizontally, vertically, or diagonally. 
The GUI is designed using JFrame, JPanel, and JButton components.

2.Requirements 
Java Development Kit (JDK) 8 or later installed on your machine.

3.Installation 
Clone or download the TicTacToe repository from GitHub. Open the project in your preferred Java development environment (e.g., IntelliJ IDEA, Eclipse). Build and run the project.

4.How to Play 
Once the game is running, use your mouse cursor to select the desired location to place a symbol(X or O), the first player to successfully form a line horizontally, vertically or diagonally wins.
(The game is based on turns, which is selected randomly)

5.Code Overview
*Main Class Main.java 
The Main class initializes the game by creating an object of the TicTacToe(); class
![image](https://github.com/efteilucian/TicTacToe/assets/102920747/106b7991-a623-4596-afad-ada86d9c0cec)



*TicTacToe.java
1st things 1st, these statements import necessary classes from the AWT (Abstract Window Toolkit), Swing, and java.util packages. 
They are used for GUI components, events, and random number generation.
in our case we use java.awt.*;
We implement the ActionListener interface. This indicates that instances of this class can listen for and respond to action events, such as button clicks.
![image](https://github.com/efteilucian/TicTacToe/assets/102920747/e25acd34-5071-443d-a9b3-a4d17a942d11)

Random random: An instance of the Random class used for generating random numbers.
JFrame frame: The main window or frame of the application.
JPanel title_panel: A panel to hold the title of the game.
JPanel button_panel: A panel to hold the Tic Tac Toe grid of buttons.
JLabel textfield: A label to display text messages, such as the current player's turn or game outcome.
JButton[] buttons: An array of 9 buttons representing the Tic Tac Toe grid.
boolean player1_turn: A boolean variable indicating whether it's currently Player 1's turn.


Afterwards we need to set up our constructor TicTacToe();
We start by setting up the frame
![image](https://github.com/efteilucian/TicTacToe/assets/102920747/40279d83-389e-4154-b416-a93dd4b6e934)
setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE): Sets the default close operation for the frame, terminating the application when the frame is closed.
setSize(800, 800): Sets the size of the frame to be 800 pixels in width and 800 pixels in height.
getContentPane().setBackground(new Color(50, 50, 50)): Sets the background color of the content pane of the frame to a dark gray color.
setLayout(new BorderLayout()): Sets the layout manager of the content pane to a BorderLayout, which is commonly used for arranging components in regions (North, South, East, West, Center).
setVisible(true): Makes the frame visible.

Next we set up the title lable (textfield)
![image](https://github.com/efteilucian/TicTacToe/assets/102920747/b6168616-2959-43b8-9c23-905c3e6cbf20)
setBackground(new Color(25, 25, 25)): Sets the background color of the textfield (JLabel) to a dark gray color.
setForeground(new Color(25, 255, 0)): Sets the foreground color of the textfield to a bright green color.
setFont(new Font("Ink Free", Font.BOLD, 75)): Sets the font of the textfield to "Ink Free" with a bold style and a size of 75.
setHorizontalAlignment(JLabel.CENTER): Centers the text horizontally within the textfield.
setText("Tic Tac Toe"): Sets the initial text of the textfield to "Tic Tac Toe".
setOpaque(true): Makes the textfield opaque, allowing its background color to be visible.

Further we set up the panels & button panels
![image](https://github.com/efteilucian/TicTacToe/assets/102920747/416e9c86-0cd2-48f4-a9c3-0a2fdbafd2b4)
setLayout(new BorderLayout()): Sets the layout manager for the title_panel to be a BorderLayout.
setBounds(0, 0, 800, 100): Sets the size and position of the title_panel.
setLayout(new GridLayout(3, 3)): Sets the layout manager for the button_panel to be a 3x3 grid layout.
setBackground(new Color(150, 150, 150)): Sets the background color of the button_panel to a light gray color.

We create & set up the buttons to the button panel
![image](https://github.com/efteilucian/TicTacToe/assets/102920747/fd406afb-1eed-431c-932f-f3fac671c5af)
The code uses a loop to create nine buttons, sets their font, makes them non-focusable, and adds an action listener (the TicTacToe instance itself, as it implements ActionListener).

In the end we add our final components to the JFrame
![image](https://github.com/efteilucian/TicTacToe/assets/102920747/18877fa3-446c-4ede-b52b-dd39601a40dc)
title_panel.add(textfield): Adds the title label (textfield) to the title_panel.
frame.add(title_panel, BorderLayout.NORTH): Adds the title_panel to the north region of the frame.
frame.add(button_panel): Adds the button_panel to the center region of the frame.

we initialize with the firstTurn(); method to determine which side starts first.


This method is used to decide player turn with the help of Thread.Sleep();
![image](https://github.com/efteilucian/TicTacToe/assets/102920747/30e9e3f9-5f85-40b6-94e1-533ea04504fb)

The method actionPerformed(ActionEvent e) does the following:
Checks if the source of the action event is the current button in the iteration
Checks if it's player 1's turn, if not, it's player 2's turn
Checks if the clicked button is empty, in case its empty set the text of the button to "X" for player 1, if not you can't place a symbol there
Switches to player 2's turn
Updates the game status label
Checks if the game has been won 
And vice versa!
![image](https://github.com/efteilucian/TicTacToe/assets/102920747/d7c2e15b-06e1-4e71-967a-6f4f5f916a60)


The check(); method allows us to see if there is any winning combination for X or O by accessing the JButton[] Array
![image](https://github.com/efteilucian/TicTacToe/assets/102920747/08c06902-c1b9-4802-873e-ebb075270813)


And in case X wins we have the following code 
![image](https://github.com/efteilucian/TicTacToe/assets/102920747/92cf98d5-8835-48b0-85ce-78b8b53c2859)






   
