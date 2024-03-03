
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {

		Scanner input = new Scanner(System.in);

		Choices(); // called from another method (Layout of the 1st page)

		String answer = input.nextLine();

		while (!answer.equals ("1")&& !answer.equals("2")&& !answer.equals("3")&& !answer.equals("4")&& !answer.equals("5")) { // loop that prompts the user to enter a correct input until it returns true 
			System.out.print("Please choose from the numbers above. Try again: ");
			answer = input.nextLine();
		}
		if (answer.equals("1")) {
			Employee_Details(); //called from another method below (Viewing employee details)
		}
		else if (answer.equals("2")) {
			Calculate_hours_worked();  //called from another method below (Calculates hours worked)
		}
		else if (answer.equals("3")) {
			Calculate_gross_weekly_salary(); //called from another method below (Calculates gross weekly/monthly salary)
		}
		else if (answer.equals("4")) {
			Calculate_net_weekly_salary(); //called from another method below (Calculates net weekly/monthly salary)
		}
		else if (answer.equals("5")) {
			System.out.println("");
			System.out.println("============ Program Terminated =============");
		}
		input.close();
	}

	// ==============================  Main method Separator  ========================================================================

	 static void Choices () {
		System.out.println("========== MotorPH Payroll System =========== ");
		System.out.println("---------------------------------------------");
		System.out.println("(1) View Employee details                   |");
		System.out.println("(2) Calculate hours worked in 1 week        |");
		System.out.println("(3) Calculate gross weekly/monthly salary   |");
		System.out.println("(4) Calculate net weekly/monthly salary     |");
		System.out.println("(5) Quit                                    |");
		System.out.println("---------------------------------------------");
		System.out.print("Please choose from the numbers above: ");
	}
	// ====================== Method separator ============================================================	

	 static void Employee_Details() { // method that views employee details
		Scanner input = new Scanner(System.in);
		System.out.println("");
		System.out.println("===========================    Viewing employee details    ===================================");

		System.out.println();
		System.out.print("Please enter employee #: ");
		int employee_number = input.nextInt();
		System.out.println("");

		while (employee_number < 10001 || employee_number > 10025) {
			System.out.print("Employee not found. Try again: ");
			employee_number = input.nextInt();

		}

		String [] Details = {"Employee #: ","Full name: ","Birthday: ","Address: ","Phone Number: ","SSS #: ","Philhealth #: ","TIN #: ","Pag-ibig #: ","Status: ","Position: ","Immediate Supervisor: ","Basic Salary: ","Rice Subsidy: ","Phone Allowance: ","Clothing Allowance: ","Gross Semi-monthly Rate: ","Hourly Rate: "};

		if(employee_number == 10001) {
			String [] emp1oyee1 = {"10001","Manuel Garcia III","10/11/1983",	"Valero Carpark Building Valero Street 1227, Makati City",	"966-860-270",	"44-4506057-3",	"820126853951",	"442-605-657-000",	"691295330870",	"Regular", "Chief Executive Officer",	"N/A",	"90000","1500",	"2000",	"1000",	"45000","535.71"};
			for (int i = 0; i <=17; i++){	
				System.out.print(Details[i]);
				System.out.println(emp1oyee1[i]);
				System.out.println("--------------------------------------------------------------------");

			}
		}

		else if (employee_number == 10002) {
			String [] employee2 = {"10002",	"Antonio Lim",	"06/19/1988",	"San Antonio De Padua 2, Block 1 Lot 8 and 2, Dasmarinas, Cavite",	"171-867-411"	,"52-2061274-9",	"331735646338"	,"683-102-776-000",	"663904995411",	"Regular",	"Chief Operating Officer",	"Garcia, Manuel III",	"60,000",	"1,500",	"2,000",	"1,000"	,"30,000",	"357.14"};
			for (int i = 0; i <=17; i++){	
				System.out.print(Details[i]);
				System.out.println(employee2[i]);
				System.out.println("--------------------------------------------------------------------");
			}
		}

		else if (employee_number == 10003) {
			String [] employee3 = {"10003",	"Lim Antonio",	"06/19/1988",	"San Antonio De Padua 2, Block 1 Lot 8 and 2, Dasmarinas, Cavite",	"171-867-411"	,"52-2061274-9",	"331735646338"	,"683-102-776-000",	"663904995411",	"Regular",	"Chief Operating Officer",	"Garcia, Manuel III",	"60,000",	"1,500",	"2,000",	"1,000"	,"30,000",	"357.14"};
			for (int i = 0; i <=17; i++){	
				System.out.print(Details[i]);
				System.out.println(employee3[i]);
				System.out.println("--------------------------------------------------------------------");
			}
		}
	}
	// ====================== Method separator ============================================================	

	 static void Calculate_hours_worked(){ // method that calculates hours worked
		Scanner input = new Scanner(System.in);
		System.out.println("");
		System.out.println("===========================    Calculating hours worked     ===================================");

		System.out.println("");
		System.out.println("Enter number of hours worked on each day: ");
		System.out.println("");
		System.out.print("MONDAY: ");
		int mon = input.nextInt();
		System.out.print("TUESDAY: ");
		int tues = input.nextInt();
		System.out.print("WEDNESDAY: ");
		int wed = input.nextInt();
		System.out.print("THURSDAY: ");
		int thurs = input.nextInt();
		System.out.print("FRIDAY: ");
		int fri = input.nextInt();
		System.out.print("SATURDAY: ");
		int sat = input.nextInt();
		System.out.print("SUNDAY: ");
		int sun = input.nextInt();
		System.out.println("==========================");
		System.out.println("You worked for "+ (mon + tues+wed+thurs+fri+sat+sun)+ " hours!");		
		input.close();
	}

	// ====================== Method separator ============================================================	

	 static void Calculate_gross_weekly_salary () { // method that calculates new weekly salary
		Scanner input = new Scanner(System.in);
		System.out.println("");
		System.out.println("===========================    Calculating gross weekly/monthly salary     ===================================");
		System.out.println("");
		System.out.print("Enter total hours worked in 1 week: ");
		double hourlyrate = input.nextDouble();
		System.out.print("Enter your hourly rate: ");
		double salary = input.nextDouble();
		System.out.println("========================================");
		System.out.printf("Your gross weekly  salary is: ₱%.2f", hourlyrate * salary);
		System.out.println();
		System.out.printf("Your gross monthly salary is: ₱%.2f", (hourlyrate * salary)*4);
		input.close();
	}

	// ====================== Method separator ============================================================	

	 static void Calculate_net_weekly_salary() { // method that calculates net weekly salary
		Scanner input = new Scanner(System.in);
		System.out.println("");
		System.out.println("===========================    Calculating net weekly/monthly salary     ===================================");		
		System.out.println("");
		System.out.print("Enter monthly salary: ");
		double salary = input.nextDouble();
		System.out.println("");
		System.out.println("Monthly Salary: "+salary);
		double SSS = 0;
		if (salary >= 24750) { // SSS deduction algorithm
			SSS = 1125.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 24250 && salary < 24750) { 
			SSS = 1102.50;	
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 23750 && salary <= 24250) { 
			SSS = 1080.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 23250 && salary <= 23750) { 
			SSS = 1057.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 22750 && salary <= 23250) { 
			SSS = 1035.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 22250 && salary <= 22750) { 	
			SSS = 1012.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 21750 && salary <= 22250) { 
			SSS = 990.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 21250 && salary <= 21750) { 
			SSS = 967.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 20750 && salary <= 21250) { 
			SSS = 945.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 20250 && salary <= 20750) { 
			SSS = 922.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 19750 && salary <= 20250) { 
			SSS = 900.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 19250 && salary <= 19750) { 
			SSS = 877.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 18750 && salary <= 19250) { 
			SSS = 855.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 18250 && salary <= 18750) { 
			SSS = 832.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 17750 && salary <= 18250) { 
			SSS = 810.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 17250 && salary <= 17750) { 
			SSS = 787.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 16750 && salary <= 17250) { 
			SSS = 765.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 16250 && salary <= 16750) { 
			SSS = 742.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 15750 && salary <= 16250) { 
			SSS = 720.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 15250 && salary <= 15750) { 
			SSS = 697.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 14750 && salary <= 15250) { 
			SSS = 675.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 14250 && salary <= 14750) { 
			SSS = 652.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 13750 && salary <= 14250) { 
			SSS = 630.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 13250 && salary <= 13750) { 
			SSS = 607.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 12750 && salary <= 13250) { 
			SSS = 585.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 12250 && salary <= 12750) { 
			SSS = 562.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 11750 && salary <= 12250) { 
			SSS = 540.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 11250 && salary <= 11750) { 
			SSS = 517.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 10750 && salary <= 11250) { 
			SSS = 495.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 10250 && salary <= 10750) { 
			SSS = 472.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 9750 && salary <= 10250) { 
			SSS = 450.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 9250 && salary <= 9750) { 
			SSS = 427.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 8750 && salary <= 9250) { 
			SSS = 405.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 8250 && salary <= 8750) { 
			SSS = 382.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 7750 && salary <= 8250) { 
			SSS = 360.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 7250 && salary <= 7750) { 
			SSS = 337.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 6750 && salary <= 7250) { 
			SSS = 315.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 6250 && salary <= 6750) { 
			SSS = 292.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 5750 && salary <= 6250) { 
			SSS = 270.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 5250 && salary <= 5750) { 
			SSS = 247.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 4750 && salary <= 5250) { 
			SSS = 225.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 4250 && salary <= 4750) { 
			SSS = 202.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 3750 && salary <= 4250) { 
			SSS = 180.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary >= 3250 && salary <= 3750) { 
			SSS = 157.50;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		else if(salary <3250) { 
			SSS = 135.00;
			System.out.println("SSS Deduction: "+ (SSS));
		}
		// ======================= End of SSS deduction algorithm =============================================
		double Philhealth = 0;
		if (salary <= 10000 ) {    // Philhealth Deduction algorithm
			Philhealth = 300;
			System.out.println("Philhealth Deduction: " + (Philhealth)/2);
		}
		else if(salary >= 10000.01 && salary <= 59999.99) {
			Philhealth = salary* 0.03/2;
			System.out.println("Philhealth Deduction: "+ Philhealth);
		}
		else if(salary >= 60000) {
			Philhealth = 1800/2;
			System.out.println("Philhealth Deduction: "+ Philhealth);
		}
		// ======================= End of Philhealth  deduction algorithm =============================================

		double pagibig = 0; // <----- PAG-IBIG DEDUCTION Algorithm
		if(salary >= 1000 && salary <=1500) {
			pagibig = Math.min( salary* 0.03, 100);
			System.out.println("Pag-ibig Deduction: "+ pagibig);
		}
		else if(salary >1500) {
			pagibig = Math.min (salary* 0.04, 100);
			System.out.println("Pag-ibig Deduction: "+ pagibig);

		}
		else if (salary <1000) {
			System.out.println("Pag-ibig Deduction: 0");
		}
		// ======================= End of Pag-ibig  deduction algorithm =============================================

		double deductions = SSS +Philhealth + pagibig;
		double total = salary - deductions;


		double Tax = 0;
		if(salary <= 20832) {						// Withholding tax algorithm
			System.out.println("Withholding Tax: 0 ");
		}
		else if(salary >= 20833 && salary <33333) {
			Tax = (total - 20833) *0.2;
			System.out.println("Withholding Tax: "+ Tax);
		}
		else if (salary >= 33333 && salary < 66667 ) {
			Tax = 2500 + (total - 33333)*0.25  ;
			System.out.println("Withholding Tax: "+ Tax);
		}
		else if (salary >= 66667 && salary < 166667 ) {
			Tax = 10833 + (total - 66667)*0.3;
			System.out.println("Withholding Tax: "+Tax);
		}
		else if (salary >= 166667 && salary < 666667) {
			Tax = 40833.33 + (total - 166667 )*0.32;
			System.out.println("Withholding Tax: "+Tax);
		}
		else if (salary >= 666667) {
			Tax = 200833.33 + (total - 666667)*0.35;
			System.out.println("Withholding Tax: "+Tax);
		}
		// ======================= End of Withholding tax  algorithm =============================================

		double finaldeductions = SSS +Philhealth + pagibig + Tax; 
		System.out.println("");
		System.out.printf("TOTAL DEDUCTIONS: %.2f " ,finaldeductions); // Total deductions. I also used "printf" to round off the centavos to 2 decimals only.
		System.out.println("");
		double finalsalary = salary - finaldeductions;
		System.out.println("=========================================");
		System.out.printf("Your net monthly salary is: ₱%.2f" ,finalsalary);
		System.out.println("");	
		System.out.printf("Your net weekly  salary is: ₱%.2f", finalsalary/4); // net monthly salary divided by 4 work weeks to get the weekly salary with deductions. Also used printf for 2 decimals only/
		input.close();
	}

}

