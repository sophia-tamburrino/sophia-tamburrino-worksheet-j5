## #1 - How does object-oriented programming pair so closely with GUIs?
The GUI components are actually objects, so we can call methods and build on them to make websites and have each GUI be able to interact with each other.

## #2 - What is the relationship between WindowListener and WindowAdapter?
In the WindowListener interface, it has methods that take in a WindowEvent object. WindowAdapter implments the WindowListener interface to specifically override the windowClosed(WindowEvent e) method. 

## #3 - What does the program below produce for a GUI? (You can sketch and upload an image or describe it – do this without running the program to make sure you understand what each line below is doing).
![My Diagram]()
## #4 - Modify the HelloGoodbyeEx2 code to update the number of times the button has been clicked on the button’s label itself.
```Java
public class HelloGoodbyeEx2 {

    public static void main(String args[]) {
        JFrame f = new JFrame();
        f.setTitle("Hello/Goodbye Ex1");
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        
        JLabel label = new JLabel("Hello");
        JButton button = new JButton("Click me!");

        //using an anonymous (static) class
        //avoids having to make ButtonClickListenerEx1 class above
        int i = 0;
        button.addActionListener(new ActionListener() {
                //implement the one method here
                //shares the name space with the whole class
                //has access to the label field above
                public void actionPerformed(ActionEvent e) {
                    if (label.getText().equals("Hello")) {
                        label.setText("Goodbye");
                    }else {
                        label.setText("Hello");
                    }

                    //where I changed the code
                    i++;
                    button.setText("" + i);
                }
            });
        
        f.add(button, BorderLayout.SOUTH);
        f.add(label, BorderLayout.NORTH);

        f.pack();
        f.setVisible(true);
        
    }
}
```
## #5 - Convert the ActionListeners to Lambda Functions.
```Java
public class RedPillBluePill extends JFrame {
    JLabel label;

    public RedPillBluePill() {
        this.setSize(300, 300);
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        JPanel panel = new JPanel(new BorderLayout());        
        JButton red = new JButton("red");
        JButton blue = new JButton("blue");
        panel.add(red, BorderLayout.EAST);
        panel.add(blue, BorderLayout.WEST);
        label = new JLabel("click a button");
        this.add(label, BorderLayout.NORTH);
        this.add(panel, BorderLayout.SOUTH);

        red.addActionListener((e) ->  {
            // TODO Auto-generated method stub
            label.setText("RED");        
        });

        blue.addActionListener((e) ->  {
            // TODO Auto-generated method stub
            label.setText("BLUE");
        });
    }
}
```

## #6 - Explain why for ActionListener you can use a Lambda function but for WindowListener you cannot?
WindowListener has a few methods that need to be implemented, and lambda functions can only work on functions that only need a single function implemented. 

## #7 - Write a program that allows you to enter a 6-digit PIN
```Java
 import javax.swing.*;
import javax.swing.border.Border;
import java.awt.*;
import java.applet.Applet;
import java.awt.event.*;

import java.awt.*;

public class BorderLayoutEx1v{

    public static void main(String args[]){

        JButton b1 = new JButton("1");
        JButton b2 = new JButton("2");
        JButton b3 = new JButton("3");
        JButton b4 = new JButton("4");
        JButton b5 = new JButton("5");
        JButton b6 = new JButton("6");
        JButton b7 = new JButton("7");
        JButton b8 = new JButton("8");
        JButton b9 = new JButton("9");
        JButton b0 = new JButton("0");
        JButton backspace = new JButton("<");
        JButton fillIn = new JButton(" ");

        JFrame f = new JFrame();
        
        JPanel left = new JPanel();
        JPanel right = new JPanel();
        JPanel cent = new JPanel();

        left.setLayout(new BorderLayout());
        right.setLayout(new BorderLayout());
        cent.setLayout(new BorderLayout());

        left.add(b1, BorderLayout.NORTH);
        left.add(b4, BorderLayout.CENTER); //gets overridden
        left.add(b7, BorderLayout.CENTER);
        left.add(backspace, BorderLayout.SOUTH);

        cent.add(b2, BorderLayout.NORTH);
        cent.add(b5, BorderLayout.CENTER);
        cent.add(b8, BorderLayout.CENTER);
        cent.add(b0, BorderLayout.SOUTH);

        right.add(b3, BorderLayout.NORTH);
        right.add(b6, BorderLayout.CENTER);
        right.add(b9, BorderLayout.CENTER);
        right.add(fillIn, BorderLayout.SOUTH);
        
        f.add(left, BorderLayout.WEST);
        f.add(cent, BorderLayout.CENTER);
        f.add(right, BorderLayout.EAST);

        f.pack(); //do alignment within the layout
        
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        f.setVisible(true);

        JTextField text = new JTextField("");

        b1.addActionListener(new ActionListener() {
            //implement the one method here
            //shares the name space with the whole class
            //has access to the label field above
            public void actionPerformed(ActionEvent e) {
                text.setText(text.getText() + "1");
            }
        });
        b2.addActionListener(new ActionListener() {
            //implement the one method here
            //shares the name space with the whole class
            //has access to the label field above
            public void actionPerformed(ActionEvent e) {
                text.setText(text.getText() + "2");
            }
        });
        b3.addActionListener(new ActionListener() {
            //implement the one method here
            //shares the name space with the whole class
            //has access to the label field above
            public void actionPerformed(ActionEvent e) {
                text.setText(text.getText() + "3");
            }
        });
        b4.addActionListener(new ActionListener() {
            //implement the one method here
            //shares the name space with the whole class
            //has access to the label field above
            public void actionPerformed(ActionEvent e) {
                text.setText(text.getText() + "4");
            }
        });
        b5.addActionListener(new ActionListener() {
            //implement the one method here
            //shares the name space with the whole class
            //has access to the label field above
            public void actionPerformed(ActionEvent e) {
                text.setText(text.getText() + "5");
            }
        });
        b6.addActionListener(new ActionListener() {
            //implement the one method here
            //shares the name space with the whole class
            //has access to the label field above
            public void actionPerformed(ActionEvent e) {
                text.setText(text.getText() + "6");
            }
        });
        b7.addActionListener(new ActionListener() {
            //implement the one method here
            //shares the name space with the whole class
            //has access to the label field above
            public void actionPerformed(ActionEvent e) {
                text.setText(text.getText() + "7");
            }
        });
        b8.addActionListener(new ActionListener() {
            //implement the one method here
            //shares the name space with the whole class
            //has access to the label field above
            public void actionPerformed(ActionEvent e) {
                text.setText(text.getText() + "8");
            }
        });
        b9.addActionListener(new ActionListener() {
            //implement the one method here
            //shares the name space with the whole class
            //has access to the label field above
            public void actionPerformed(ActionEvent e) {
                text.setText(text.getText() + "9");
            }
        });
        b0.addActionListener(new ActionListener() {
            //implement the one method here
            //shares the name space with the whole class
            //has access to the label field above
            public void actionPerformed(ActionEvent e) {
                text.setText(text.getText() + "0");
            }
        });
        backspace.addActionListener(new ActionListener() {
            //implement the one method here
            //shares the name space with the whole class
            //has access to the label field above
            public void actionPerformed(ActionEvent e) {
                text.setText(text.getText() + "0");
            }
        });
    }
}       

```
