# Project Title

Just after the title, introduce your project by describing attractively what the project is about and what is the main problem that inspires you to create this project or what is the main contribution for the potential user of your project.

---

## Technologies

Describe the technologies required to use your project such as programming languages, libraries, frameworks, and operating systems. Be sure to include the specific versions of any critical dependencies that you have used in the stable version of your project.

---

## Installation Guide


Steps to run:
1) type ./data/daily_rate_sheet.csv when prompted by application
2) enter user data as prompted
3) If user chooses to save results, they will be saved to ./data/your_qualifying_loans.csv

Code added to write CSV:
def save_csv_data(qualifying_loans):
    your_qualifying_loans = Path("./data/your_qualifying_loans.csv")
    with open(your_qualifying_loans, 'w', newline='') as file:
        csvwriter = csv.writer(file)
        csvwriter.writerows([ qualifying_loans])
    return qualifying_loans

Code added to prompt user to save or not save results:
 *function to ask whether to save results to a csv. System will save to a csv file named "your_qualifying_loans.csv" if the user chooses to save. System will exit if user does not want to save reults.*
def save_data(qualifying_loans):

    output = questionary.text("Do you want to save your qualifying loans as a csv file (enter 'yes' or 'no')?").ask()
    if output == 'yes':
        output = save_csv_data(qualifying_loans)
        sys.exit("Thanks! Your results have been saved to a csv file called 'your_qualifying_loans.csv'.")
    else:
        sys.exit("Thanks for using this program")


---

## Usage

Here is an example of this application's functionality:
? Enter a file path to a rate-sheet (.csv): ./data/daily_rate_sheet.csv
? What's your credit score? 650
? What's your current amount of monthly debt? 200
? What's your total monthly income? 8000
? What's your desired loan amount? 20000
? What's your home value? 400000
The monthly debt to income ratio is 0.03
The loan to value ratio is 0.05.
Found 8 qualifying loans
? Do you want to save your qualifying loans as a csv file (enter 'yes' or 'no')? yes
Thanks! Your results have been saved to a csv file called 'your_qualifying_loans.csv'.

If no qualifying loans, the app notifies user and exits the app.
If the user does not want to save his/her results, then the app exits.

---

## Contributors

Angela Richter is the sole contributor to this app.

---

## License

This code should not be used for real world personal or professional financing situations.
