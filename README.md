# Racecar-Project
stimulation of driving a race car(beginner project)

package app;
import java.util.Scanner;

public class RaceCar {

	private String engine;
	private int tires;
	private String color;
	
	public RaceCar(String engine, int tires, String color) {
		this.engine = engine;
		this.tires = tires;
		this.color = color;
		
	}
	public String getEngine() {
		return engine;
	}
	public int getTires() {
		return tires;
	}
	public String getColor() {
		return color;
	}
	public void TurnOn() {
		System.out.println("The car has been turned on");
	}
	public void CantStart() {
		System.out.println("Well, looks like you cant drive it then. Better luck next time.");
	}
	public void CheckPsi() {
		System.out.println("The psi of the tires are at least 32");
	}
	public void Stop() {
		System.out.println("The car has stopped!");
	}
	public void Drive() {
		System.out.println("The car is driving, watch the speed! There may be cops!");
	}
	public void PullOver() {
		System.out.println("Oh no, you were caught not dirivng the speed limit! You better pull over!");
	}
	public void Restart() {
		System.out.println("That ticket looks expensive, lets restart the car!");
	}
	
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Scanner UserIn = new Scanner(System.in);
		String yes = "yes";
		String no = "no";
		int answer = 60;
		
		//finding car
		RaceCar Car = new RaceCar("tiwn-turbo v8", 4, "red");
		System.out.println("You walk up to a " + Car.getColor() +" sports car with " + Car.getTires() + " tires with a " + Car.getEngine() +" engine");
		System.out.println("You take a look at the tires. Are the psi at least 32? yes/no");
		UserIn.nextLine();
		
		//start car options
		while(UserIn.nextLine().equals("yes")) {
			System.out.println("You get in the car.");
			Car.TurnOn();
			System.out.println("You begin driving and turn onto the freeway, the speedlimit is 60 how fast should you go?");
			UserIn.nextInt();
			//checking speed
			while(UserIn.nextInt() == answer) {
				Car.Drive();
				//checking speed again for restart and stop
				System.out.println("Wanna see how fast this racecar can really drive? yes/no");
				UserIn.nextLine();
				while(UserIn.nextLine().equals("yes")) {
					Car.PullOver();
					Car.Stop();
					Car.Restart();
					break;
				}
			}
			//cant drive it due to psi
			{System.out.println("Uh oh! You got pulled over");
			Car.Stop();
			Car.Restart();
			}
		break; }
		while(UserIn.nextInt() != answer){Car.CantStart();
		}
		
	}

}
