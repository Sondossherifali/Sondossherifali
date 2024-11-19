Student Management System

# Global list to store student records
student_records = []

# Function to add a new student
def add_student():
    student_id = input("Enter Student ID: ")
    name = input("Enter Student Name: ")
    age = input("Enter Student Age: ")
    grade = input("Enter Student Grade: ")
    
    student = {
        "ID": student_id,
        "Name": name,
        "Age": age,
        "Grade": grade
    }
    student_records.append(student)
    print("Student added successfully!")

# Function to delete a student by ID
def delete_student():
    student_id = input("Enter the Student ID to delete: ")
    for student in student_records:
        if student["ID"] == student_id:
            student_records.remove(student)
            print("Student record deleted successfully!")
            return
    print("Student not found!")

# Function to display all student records
def display_students():
    if not student_records:
        print("No student records found.")
    else:
        print("Student Records:")
        for student in student_records:
            print(f"ID: {student['ID']}, Name: {student['Name']}, Age: {student['Age']}, Grade: {student['Grade']}")

# Main menu
def main():
    while True:
        print("\nStudent Management System")
        print("1. Add Student")
        print("2. Delete Student")
        print("3. Display Students")
        print("4. Exit")
        
        choice = input("Enter your choice: ")
        
        if choice == "1":
            add_student()
        elif choice == "2":
            delete_student()
        elif choice == "3":
            display_students()
        elif choice == "4":
            print("Exiting the system. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

# Run the program
if __name__ == "__main__":
    main()
