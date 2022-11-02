import pymongo
client = pymongo.MongoClient('mongodb://127.0.0.1:27017/')  # Connecting to mongodb localhost database
db = client['Telephone_Directory']                          # Creating Database in mongodb
collection = db.Details                                     # Creating Collection inside Database

def choose():
    print('C - Create Data, R - Read Data, U - Update Data, D - Delete Data')
    print('Choose any one of the letter (C, R, U, D) to proceed with the Telephone Directory')
    choice = input('Enter any one operation : ')
    if choice == 'C' or choice == 'c' :
        create()
    elif choice == 'R' or choice == 'r' :
        read()
    elif choice == 'U' or choice == 'u' :
        update()
    elif choice == 'D' or choice == 'd' :
        delete()
    else :
        print('Read the below instructions carefully')
        choose()

def create():
    name = input('Enter Name : ')
    phone_no = input('Enter Phone No : ')
    address = input('Enter Address : ')
    collection.insert_one({'Name' : name, 'Phone_No' : phone_no, 'Address' : address})
    print('A - Add more data to the Telephone Directory, any other characters - Stop adding data to the Telephone Directory')
    add_more = input('Enter A or other Characters : ')
    if add_more == 'A' or add_more == 'a' :
        create()
    else : print('Data Created Successfully')

def read():
    print('F - Read full Telephone Directory, N - Search with Name in Telephone Directory \n'
          'P - Search with Phone number in Telephone Directory, A - Search with Address in Telephone Directory')
    read_choice = input('Choose between F, N, P and A : ')
    if read_choice == 'F' or read_choice == 'f' :
        for i in collection.find():
            print(i)
    elif read_choice == 'N' or read_choice == 'n' :
        read_name = input('Enter name to search : ')
        for i in collection.find({'Name' : read_name}):
            print(i)
    elif read_choice == 'P' or read_choice == 'p' :
        read_phone = input('Enter phone_no to search : ')
        for i in collection.find({'Phone_No' : read_phone}):
            print(i)
    elif read_choice == 'A' or read_choice == 'a' :
        read_address = input('Enter address to search : ')
        for i in collection.find({'Address' : read_address}):
            print(i)
    else :
        print('Read the below instructions carefully')
        read()

def update():
    print('Update the directory with Phone Number')
    update_phone = input('Enter Phone Number to update the other details in the data : ')
    update_name_choice = input("Enter the name to update or type 'noupdate' : ")
    update_address_choice = input("Enter the Address to update or type 'noupdate' : ")
    if update_name_choice == 'noupdate' and update_address_choice != 'noupdate' :
        collection.update_one({'Phone_No' : update_phone}, {'$set' : {'Address' : update_address_choice}})
    elif update_name_choice != 'noupdate' and update_address_choice == 'noupdate' :
        collection.update_one({'Phone_No' : update_phone},{'$set' : {'Name' : update_name_choice}})
    elif update_name_choice != 'noupdate' and update_address_choice != 'noupdate' :
        collection.update_one({'Phone_No' : update_phone}, {'$set' : {'Name' : update_name_choice, 'Address' : update_address_choice}})

def delete():
    print('Delete the data of the directory with Phone Number')
    delete_phone = input('Enter the Phone Number to delete data : ')
    collection.delete_one({'Phone_No' : delete_phone})


if __name__=='__main__':
    choose()
