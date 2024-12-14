# OE-2

class Phone:
    def __init__(self, brand, model, version):
        self.brand = brand
        self.model = model
        self.version = version

    def __str__(self):
        return f"{self.brand} {self.model} {self.version}"

    def update_brand(self, brand):
        self.brand = brand

    def update_model(self, model):
        self.model = model

    def update_version(self, version):
        self.version = version

    def delete_brand(self):
        del self.brand

    def delete_model(self):
        del self.model

    def delete_version(self):
        del self.version


def display_menu():
    print("\n♡♡General About♡♡")
    print("1. Create a Phone")
    print("2. Modify a Phone")
    print("3. Delete a Phone")
    print("4. List Phones")
    print("5. Exit")


def create_phone(phoneList):
    brand = input("Enter phone brand: ")
    model = input("Enter phone model: ")
    version = input("Enter phone version: ")
    phone = Phone(brand, model, version)
    phoneList.append(phone)
    print("Phone created successfully!")


def modify_phone(phoneList):
    list_phones(phoneList)
    index = int(input("Enter the index of the phone to modify: ")) - 1
    if 0 <= index < len(phoneList):
        phone = phoneList[index]
        print("1. Update Brand")
        print("2. Update Model")
        print("3. Update Version")
        choice = int(input("Choose an option: "))
        if choice == 1:
            new_brand = input("Enter new brand: ")
            phone.update_brand(new_brand)
        elif choice == 2:
            new_model = input("Enter new model: ")
            phone.update_model(new_model)
        elif choice == 3:
            new_version = input("Enter new version: ")
            phone.update_version(new_version)
        else:
            print("Invalid choice.")
        print("Phone updated successfully!")
    else:
        print("Invalid index.")


def delete_phone(phoneList):
    list_phones(phoneList)
    index = int(input("Enter the index of the phone to delete: ")) - 1
    if 0 <= index < len(phoneList):
        del phoneList[index]
        print("Phone deleted successfully!")
    else:
        print("Invalid index.")


def list_phones(phoneList):
    if phoneList:
        for idx, phone in enumerate(phoneList, start=1):
            print(f"{idx}. {phone}")
    else:
        print("No phones available.")


def main():
    phoneList = []
    while True:
        display_menu()
        choice = int(input("Choose an option: "))
        if choice == 1:
            create_phone(phoneList)
        elif choice == 2:
            modify_phone(phoneList)
        elif choice == 3:
            delete_phone(phoneList)
        elif choice == 4:
            list_phones(phoneList)
        elif choice == 5:
            print("Thankyou!♡♡♡")
            break
        else:
            print("Invalid choice. Please try again.")


if __name__ == "__main__":
    main()

        
        
    
        
