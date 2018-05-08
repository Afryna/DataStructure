# DataStructure
import javax.swing.JOptionPane;

import java.util.Scanner;
/**
 *
 * @author afryn
 */
public class DataStructure {


    static Movies obj[] = new Movies[5];


    public static void main(String[] args) {


        Scanner in = new Scanner(System.in);


        int choice3 = 0;

        do {

            String schoice = JOptionPane.showInputDialog("Movie Fixtures\n\nChoose the movie whose fixtures you want to be displayed\n\n1. Avangers \n2. Gonjiam\n3. Ant Man\n4. Truth or Dare\n5. Quiet Place\n\nEnter your choice or enter -1 to quit: ");

            int choice = Integer.parseInt(schoice);

            switch (choice) {

                case 1:

                    teamMenu(0, "Avangers");

                    break;


                case 2:

                    teamMenu(1, "Gonjiam");

                    break;


                case 3:

                    teamMenu(2, "Ant Man");

                    break;


                case 4:

                    teamMenu(3, "Truth or Dare");

                    break;


                case 5:

                    teamMenu(4, "Quiet Place");

                    break;


                case -1:

                    choice3 = -1;

                    break;

                default:

                    System.out.print("Invalid option! Press 1 to enter once again or -1 to exit: ");

                    choice3 = in.nextInt();

            }

        }
 while (choice3 != -1);

    }


    public static void teamMenu(int teamIndex, String teamName) {

        Scanner in = new Scanner(System.in);

        int choice2;

        int choice4;

        obj[teamIndex] = new Movies();

        obj[teamIndex].autoPop();


        choice2 = 0;

        do {

            String schoice1 = JOptionPane.showInputDialog("" 
                    + teamName + "\n\n1. All times available\n2. All upcoming movie times\n3.Now showing time "
                            + "\n\nEnter your "
                            + "choice or -1 to go back to the previous menu: ");

            int choice1 = Integer.parseInt(schoice1);

            switch (choice1) {

                case 1:

                    choice4 = 0;

                    do {

                        String schoice5 = JOptionPane.showInputDialog("Next movie:  \n\n**************************************\n " 
                                + obj[teamIndex].peek()+          "\n**************************************" + "\n\n1. Buy a ticket for this movie"
                                        + "\n2. Change movie"
                                        + "\n3. Display the number of tickets you want to buy"
                                        + "\n\nEnter your choice or -1 to go back to the previous menu: ");

                        int choice5 = Integer.parseInt(schoice5);

                        switch (choice5) {

                            case 1:

                                obj[teamIndex].buyticketsnext();

                                break;

                            case 2:

                                obj[teamIndex].cancelticketnext();

                                break;

                            case 3:

                                obj[teamIndex].displayStatus();

                                break;

                            case -1:

                                choice4 = -1;

                                break;

                            default:

                                String schoice4 = JOptionPane.showInputDialog("Invalid choice! Press 1 to enter once again or -1 to go back to the previous menu: ");

                                choice4 = Integer.parseInt(schoice4);

                        }

                    }
 while (choice4 != -1);

                    break;

                case 2:

                    obj[teamIndex].displayStack();

                    break;

                case -1:

                    choice2 = -1;

                    break;

                default:

                    String schoice2 = JOptionPane.showInputDialog("Invalid choice! Press 1 to enter once again or -1 to go back to the previous menu: ");

                    choice2 = Integer.parseInt(schoice2);

            }

        }
 while (choice2 != -1);

    }

}
