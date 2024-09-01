Contact List CRUD Application

1. Project Overview

The Contact List CRUD Application is a command-line interface (CLI) tool developed using Python. It enables users to manage a list of contacts by performing four essential operations: Create, Read, Update, and Delete (CRUD). This project is designed for beginners, offering a practical introduction to Python programming and data management.

2. Project Objectives

To understand the CRUD operations that form the basis of most applications that handle data.
To develop a functional CLI application that interacts with users to manage a list of contacts.
To practice Python programming skills, including functions, loops, conditionals, and error handling.

3. Project Features

3.1 Create Operation
Functionality: Allows users to add a new contact to the list by entering the name, phone number, and email address.
Implementation: 
Collects user input for the contact details.
Stores the contact in a dictionary.
Appends the dictionary to a list of contacts.

def create_contact():
    name = input("Enter contact name: ")
    phone = input("Enter contact phone number: ")
    email = input("Enter contact email: ")

    contact = {"name": name, "phone": phone, "email": email}
    contacts.append(contact)
    print("Contact added successfully!")

3.2 Read Operation
Functionality: Displays all the contacts in the list.
Implementation:
Iterates over the list of contacts.
Prints each contact's details in a formatted manner.

def read_contacts():
    if len(contacts) == 0:
        print("No contacts found.")
    else:
        for idx, contact in enumerate(contacts):
            print(f"{idx + 1}. {contact['name']} | {contact['phone']} | {contact['email']}")

3.3 Update Operation
Functionality: Allows users to modify the details of an existing contact.
Implementation:
Displays the list of contacts.
Prompts the user to select a contact to update.
Allows the user to enter new details, retaining the old ones if the input is left blank.

def update_contact():
    read_contacts()
    index = int(input("Enter the number of the contact you want to update: ")) - 1
    
    if 0 <= index < len(contacts):
        name = input("Enter new contact name (leave empty to keep current): ")
        phone = input("Enter new contact phone number (leave empty to keep current): ")
        email = input("Enter new contact email (leave empty to keep current): ")

        if name:
            contacts[index]["name"] = name
        if phone:
            contacts[index]["phone"] = phone
        if email:
            contacts[index]["email"] = email

        print("Contact updated successfully!")
    else:
        print("Invalid contact number.")

3.4 Delete Operation
Functionality: Removes a contact from the list based on the user’s selection.
Implementation:
Displays the list of contacts.
Prompts the user to select a contact to delete.
Removes the selected contact from the list.

def delete_contact():
    read_contacts()
    index = int(input("Enter the number of the contact you want to delete: ")) - 1
    
    if 0 <= index < len(contacts):
        contacts.pop(index)
        print("Contact deleted successfully!")
    else:
        print("Invalid contact number.")

4. User Interface

The application features a simple menu-driven interface that guides users through the CRUD operations. The menu is displayed in a loop, allowing users to perform multiple operations until they choose to exit.

def menu():
    while True:
        print("\nContact List Application")
        print("1. Add Contact")
        print("2. View Contacts")
        print("3. Update Contact")
        print("4. Delete Contact")
        print("5. Exit")
        
        choice = input("Enter your choice: ")

        if choice == '1':
            create_contact()
        elif choice == '2':
            read_contacts()
        elif choice == '3':
            update_contact()
        elif choice == '4':
            delete_contact()
        elif choice == '5':
            break
        else:
            print("Invalid choice. Please try again.")

5. Code Execution

To run the application, ensure you have Python installed on your system. Save the code in a file named `crud_app.py`, and execute the file using a Python interpreter. The application will start, displaying the menu for the user to interact with.

python crud_app.py

6. Potential Improvements

File Handling: Implement file handling to save contacts to a file (e.g., CSV or JSON) and load them when the application starts.
Search Functionality: Add a search feature to find contacts by name or phone number.
Input Validation: Implement validation checks to ensure correct and complete input (e.g., valid email addresses and phone numbers).
User Authentication: Add a login system to secure the application and manage different user profiles.

7. Conclusion

The Contact List CRUD Application is a foundational project for beginners. It introduces essential programming concepts in Python and provides a practical understanding of how data management works in real-world applications.