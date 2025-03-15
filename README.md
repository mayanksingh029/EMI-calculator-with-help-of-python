# EMI-calculator-with-help-of-python
It is usefull to calculate EMI at any rate of interest in how much time you take for EMI
def calculate_emi(principal, annual_interest_rate, tenure_years):
    # Convert annual interest rate to monthly and tenure in years to months
    monthly_interest_rate = annual_interest_rate / (12 * 100)
    tenure_months = tenure_years * 12
    
    # EMI formula
    emi = (principal * monthly_interest_rate * (1 + monthly_interest_rate) ** tenure_months) / \
          ((1 + monthly_interest_rate) ** tenure_months - 1)
    
    return emi

def main():
    # User input for principal amount, annual interest rate, and loan tenure
    principal_amount = float(input("Enter the loan amount: "))
    annual_interest_rate = float(input("Enter the annual interest rate (in percentage): "))
    loan_tenure_years = int(input("Enter the loan tenure (in years): "))
    
    emi = calculate_emi(principal_amount, annual_interest_rate, loan_tenure_years)
    print(f"The EMI for a loan amount of {principal_amount} at an annual interest rate of {annual_interest_rate}% for {loan_tenure_years} years is: {emi:.2f}")

if __name__ == "__main__":
    main()
    
