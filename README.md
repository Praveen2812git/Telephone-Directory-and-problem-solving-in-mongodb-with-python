# Telephone-Directory-in-mongodb-with-python
A simple telephone directory with CRUD operations using mongodb in python.

## Explanation
- There are four operations in Telephone Directory called CRUD operations. They are Create, Read, Update and Delete
- **CREATE -** Creates data with the user given data.
  - Name
  - Phone Number
  - Address
  
- **READ -** Reads the stored data in the Telephone Directory. There are different ways to read.
  - F or f - Reads the full telephone directory.
  - N or n - Reads the telephone directory with only the name user proceeds with.
  - P or n - Reads the telephone directory with only the phone number user proceeds with.
  - A or a - Reads the telephone directory with only the address user proceeds.

- **UPDATE -** Selects the data with the phone number and updates the data with the name or address (or) both name and address.

- **DELETE -** Deletes the data with the phone number user proceeds with.

## Requirements
- Mongodb database in PC
- Installation of pymongo library in python
  - pip install pymongo (Run this in terminal to install pymongo module)
