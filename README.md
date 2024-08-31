# Contact-List-CRUD-Application

contacts = []

def create_contact():
    name = input("Enter contact name: ")
    phone = input("Enter contact phone number: ")
    email = input("Enter contact email: ")
		
    contact = {"name": name, "phone": phone, "email": email}
    contacts.append(contact)
    print("Contact added successfully!")

	def read_contacts():
    if len(contacts) == 0:
        print("No contacts found.")
    else:
        for idx, contact in enumerate(contacts):
            print(f"{idx + 1}. {contact['name']} | {contact['phone']} | {contact['email']}")
						
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
				
	def delete_contact():
    read_contacts()
    index = int(input("Enter the number of the contact you want to delete: ")) - 1
    
    if 0 <= index < len(contacts):
        contacts.pop(index)
        print("Contact deleted successfully!")
    else:
        print("Invalid contact number.")

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
						
	if __name__ == "__main__":
    menu()
