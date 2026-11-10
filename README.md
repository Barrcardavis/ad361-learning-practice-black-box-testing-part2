# ad361-learning-practice-black-box-testing-part2

## Step 1: Identify Conditions and Actions
### Conditions
Dates are valid (check-in before checkout)
Number of nights is between 1 and 31
Number of guests is between 1 and 12
Requested nights are available
More than five guests
### Actions
Create reservation
Calculate standard price
Add extra guest fee
Raise ValueError
Raise UnavailableError

## Step 2: Create a Decision Table
<img width="769" height="418" alt="image" src="https://github.com/user-attachments/assets/f2615881-804d-491e-8312-ac5a58d09a37" />

## Step 3: Decision Table Test Cases

### TC01: Valid Reservation Without Extra Guest Fee
Check-in: October 1
Checkout: October 4
Guests: 4
Availability: Available
Expected Action: Create reservation
Expected Price:
3 nights × $200 = $600
Cleaning fee = $50
Total = $650

### TC02: Valid Reservation With Extra Guest Fee
Check-in: October 1
Checkout: October 4
Guests: 7
Availability: Available
Expected Action: Create reservation and add extra guest fee
Expected Price:
3 nights × $200 = $600
Cleaning fee = $50
2 extra guests × $25 × 3 nights = $150
Total = $800

### TC03: Invalid Dates
Check-in: October 10
Checkout: October 8
Guests: 4
Availability: Available
Expected Action: Raise ValueError
Expected Exception: ValueError

### TC04: Invalid Number of Nights
Check-in: October 1
Checkout: November 5
Guests: 4
Availability: Available
Expected Action: Raise ValueError
Expected Exception: ValueError

### TC05: Invalid Number of Guests
Check-in: October 1
Checkout: October 4
Guests: 13
Availability: Available
Expected Action: Raise ValueError
Expected Exception: ValueError

### TC06: Unavailable Reservation
Check-in: October 1
Checkout: October 4
Guests: 4
Availability: One or more nights unavailable
Expected Action: Raise UnavailableError
Expected Exception: UnavailableError

## Step 4: Identify Reservation States and Events
### Reservation States
Pending
Confirmed
Checked In
Completed
Cancelled
### Events
Payment succeeds
Payment fails
Guest cancels reservation
Guest checks in
Guest checks out

## Step 5: Create a State Transition Table
<img width="764" height="375" alt="image" src="https://github.com/user-attachments/assets/b9856c00-b767-4726-99f8-4a338c16b3bd" />

## Step 6: State Transition Test Cases
<img width="883" height="312" alt="image" src="https://github.com/user-attachments/assets/9fcaca3a-ecb3-41f3-b5c0-107d9997c1b3" />

