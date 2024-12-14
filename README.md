bank.py


balance = 0.0

while True:
    print('Menu')
    print("1.Make Transaction")
    print("2.Show Account Balance")
    print("3.Exit")
    ch = int(input("Enter your choice : "))
    if ch == 1:
        s = input("Enter the transaction string : ")
        amount = float(s.split()[1])
               
        if s.lower()[0] == 'd': #deposit
            if amount < 0:
                print('Amount can\'t be less than zero')
            else:
                balance += amount
                print("Deposit Done!")
        else: #withdrawal
            if amount < 0:
                print('Amount can\'t be less than zero')
            else:
                if amount > balance:
                    print("\aInsufficient balance!")
                else:
                    balance -= amount
                    print("Withdrawal Done!")   
    elif ch == 2:
        print('Current Balance is, Rs.', balance)
    elif ch == 3:
        break
