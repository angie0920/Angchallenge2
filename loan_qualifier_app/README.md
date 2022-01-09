# Loan Qualifier App - Challenge 2 Submission

This is an app that prompts the user for a few key pieces of information to determine if the user qualifies for a loan. If the user does qualify for loans, the user can choose whether to save the results to a csv file.

---

## Technologies

Main technology is python code organized as modules. The file app.py pulls other functions from files located in subfolders.

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
