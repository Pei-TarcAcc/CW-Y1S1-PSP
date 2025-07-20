Title- hair styling & color

Function for each module:
Customer:View department info, booking, payment

Expert:View assign customer, view salary

Admin:View overall Schedule, View customer list, generate sales report

Type info:
- Services:
  - Hair Cut – RM80
  - Hair Coloring – RM150
  - Rebonding Treatment – RM250

- Experts:
  - Lily – Hair Stylist (10AM–4PM)
  - Jay – Color Specialist (10AM–4PM)
  - Amira – Treatment Expert (10AM-4PM)

Psutocode:
<Main menu>
START
    DISPLAY welcome screen and logo
    LOOP UNTIL user selects 'Exit'
        DISPLAY main menu:
            1. Customer Login
            2. Expert Login
            3. Admin Login
            4. Exit

        READ userChoice

        SWITCH userChoice
            CASE 1: CALL CustomerModule()
            CASE 2: CALL ExpertModule()
            CASE 3: CALL AdminModule()
            CASE 4: DISPLAY exit message and END
            DEFAULT: DISPLAY "Invalid option. Try again."
        END SWITCH
    END LOOP
END

<Customer>
FUNCTION CustomerModule()
    LOOP UNTIL user selects 'Exit'
        DISPLAY menu:
            1. View Centre Info
            2. View Services & Experts
            3. Check Appointment Availability
            4. Book Appointment
            5. Make Payment
            6. View My Bookings
            7. Exit

        READ customerChoice

        SWITCH customerChoice
            CASE 1: CALL DisplayCentreInfo()
            CASE 2: CALL ShowServicesAndExperts()
            CASE 3: CALL CheckAvailability()
            CASE 4: CALL BookAppointment()
            CASE 5: CALL MakePayment()
            CASE 6: CALL ViewBookings()
            CASE 7: RETURN to main menu
            DEFAULT: DISPLAY "Invalid selection."
        END SWITCH
    END LOOP
END FUNCTION

<Expert>
FUNCTION ExpertModule()
    AUTHENTICATE expert login
    LOOP UNTIL expert selects 'Exit'
        DISPLAY expert menu:
            1. View Schedule
            2. View Assigned Customers
            3. View Bonus Entitlement
            4. Exit

        READ expertChoice

        SWITCH expertChoice
            CASE 1: CALL DisplayExpertSchedule()
            CASE 2: CALL DisplayAssignedCustomers()
            CASE 3: CALL CalculateBonus()
            CASE 4: RETURN to main menu
            DEFAULT: DISPLAY "Invalid selection."
        END SWITCH
    END LOOP
END FUNCTION

<Admin>
FUNCTION AdminModule()
    AUTHENTICATE admin login
    LOOP UNTIL admin selects 'Exit'
        DISPLAY admin menu:
            1. View Individual Expert Schedule
            2. View Overall Schedule
            3. View Customer List
            4. Generate Sales Report
            5. View Expert Bonus Entitlement
            6. Exit

        READ adminChoice

        SWITCH adminChoice
            CASE 1: CALL ShowExpertSchedule()
            CASE 2: CALL ShowAllSchedules()
            CASE 3: CALL ShowCustomerList()
            CASE 4: CALL GenerateSalesReport()
            CASE 5: CALL ShowExpertBonus()
            CASE 6: RETURN to main menu
            DEFAULT: DISPLAY "Invalid selection."
        END SWITCH
    END LOOP
END FUNCTION
