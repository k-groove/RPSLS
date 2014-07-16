/*rules of game "scissors cut paper", "paper covers rock", "rock crushes lizard",
    "lizard poisons spock", "spock smashes scissors", "scissors decapitate lizard", "lizard eats paper",
    "paper disproves spock", "spock vaporizes rock", "rock crushes scissors"]*/
import java.util.Scanner;
public class Rpsls {
	public static void main(String[] args) {
	String[]hands = {"rock","paper","scissors","lizard","spock"};
	int computerHand;
	int humanHand = 6;
	Scanner scan = new Scanner(System.in);
	System.out.println("Choose: rock, paper, scissors, lizard, or spock");
	String humanInput = scan.next().toUpperCase();
	switch (humanInput){
	case "ROCK": humanHand = 0;
		break;
	case "PAPER": humanHand = 1;
		break;
	case "SCISSORS": humanHand = 2;
		break;
	case "LIZARD": humanHand = 3;
		break;
	case "SPOCK": humanHand = 4;
		break;	
	}
	computerHand = (int)(Math.random()*4);
	//System.out.println(computerHand);
	if (computerHand == 0)
		System.out.println("Computer plays ROCK.");
	if (computerHand == 1)
		System.out.println("Computer plays PAPER.");
	if (computerHand == 2)
		System.out.println("Computer plays SCISSORS.");
	if (computerHand == 3)
		System.out.println("Computer plays LIZARD.");
	if (computerHand == 4)
		System.out.println("Computer plays SPOCK.");	
	whoWins(humanHand, computerHand);	
		}
	public static void whoWins(int human, int computer){
	int[][] winningMatrix ={{ 0,-1, 1, 1,-1},
                			{ 1, 0,-1,-1, 1},
                			{-1, 1, 0, 1,-1},
                			{-1, 1,-1, 0, 1},
                			{ 1, 1,-1,-1, 0}};
	if (winningMatrix[human][computer] == 0)
		System.out.println("TIE");
	if (winningMatrix[human][computer] == 1)
		System.out.println("YOU WIN!");
	if (winningMatrix[human][computer] == -1)
		System.out.println("YOU LOSE!");
	}
}
