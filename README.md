# Student Management System

students = {}

while True:
    print("\n===== Student Management System =====")
    print("1. Add Student")
    print("2. View Students")
    print("3. Search Student")
    print("4. Update Student")
    print("5. Delete Student")
    print("6. Exit")

    choice = input("Enter your choice (1-6): ")

    if choice == "1":
        roll_no = input("Enter Roll Number: ")
        name = input("Enter Student Name: ")
        marks = input("Enter Marks: ")

        students[roll_no] = {
            "Name": name,
            "Marks": marks
        }

        print("✅ Student Added Successfully!")

    elif choice == "2":
        if len(students) == 0:
            print("No student records found.")
        else:
            print("\n--- Student Records ---")
            for roll_no, details in students.items():
                print(f"Roll No: {roll_no}")
                print(f"Name: {details['Name']}")
                print(f"Marks: {details['Marks']}")
                print("----------------------")

    elif choice == "3":
        roll_no = input("Enter Roll Number to Search: ")

        if roll_no in students:
            print("\nStudent Found:")
            print("Name:", students[roll_no]["Name"])
            print("Marks:", students[roll_no]["Marks"])
        else:
            print("❌ Student Not Found!")

    elif choice == "4":
        roll_no = input("Enter Roll Number to Update: ")

        if roll_no in students:
            new_name = input("Enter New Name: ")
            new_marks = input("Enter New Marks: ")

            students[roll_no]["Name"] = new_name
            students[roll_no]["Marks"] = new_marks

            print("✅ Student Updated Successfully!")
        else:
            print("❌ Student Not Found!")

    elif choice == "5":
        roll_no = input("Enter Roll Number to Delete: ")

        if roll_no in students:
            del students[roll_no]
            print("✅ Student Deleted Successfully!")
        else:
            print("❌ Student Not Found!")

    elif choice == "6":
        print("Thank You!")
        break

    else:
        print("❌ Invalid Choice! Please enter 1-6.")# Student--Management-system.py

