       (class work)

# print("              if else")
# a=int(input("Enter your number:"))
# if a%2==0:
#     print("The given number is an even number")
# else:
#     print("Yor given number is odd")





# print("                only if ")
# num1=int(input("Enter your first number:"))
# num2=int(input("Enter your Second number:"))
# num3=int(input("Enter your Third number:"))





# if num1>num2 and num1>num3:
#     print("Your First number is the Greatest");
# if num2>num3 and num2>num1:
#     print("Your Second number is the Greatest");
# if num3>num1 and num3>num2:
#     print("Your Third number is the Greatest");





# # print(              "if and else")
# age=int(input("Enter your age:"))





# if age>=18:
#   print("You are eligible to vote")
# else:
#   print("You are not eligible to vote")





# print("                if elif else"  )
# number= int(input("Enter a number:"))
# if number==10:
#   print("Your given number is 10")
# elif number==50:
#   print("Your given number is 50")
# elif number==20:
#   print("Your given number is 20")
# elif number==70:
#   print("Your given number is 70")
# else:
#   print("Your given number is not 10,20,50 or 70")





# print("                for loop")
# languages=["Urdu","English","Arabic", "Pashto", "Hindi"]
# for language in languages:
#   print(language)





# #print("                While Loop")
# num=0
# while num <10:
#   print(f"number is {num}")
#   num=num+1





# print("                  math.sqrt")
# import math
# x= math.sqrt(4)
# print("Your answer is:", x)





# print("                   math.ceilfloor")
# import math
# x= math.ceil(1.4)
# y=math.floor(1.4)
# print("Your answer is:",x)





# print("                    Function")
# def fun():
#     print("AJ ka kam")
# fun()





# print("                  Function with argument)

# def add (a,b):
#   return a+b
# def istrue (a):
#   return bool (a)

# res=add(2,3)
# print("Result of add function is {} ".format (res))
# res=istrue (2<5)
# print("\nresult of istrue function is {}".format(res))





#  print("                Function with default argument to find age")
# ages={"Salman":15, "Ahmed":16, "Ali":17, "Asghar": 29}
# print (ages["Asghar"])




#  print("                Function with default argument to print studnets names")
# ages={"Salman":15, "Ahmed":16, "Ali":17, "Asghar": 29}
# for students in ages:
#   print (students)





# print("                    Arrays")
# ages= [23,25,24,27,28]
# print("All ages:",ages)





#  print("                Indexing")
# languages=["Urdu","English","Arabic", "Pashto", "Hindi"]
# print(languages[3])





#  print("                Slicing Indexing")
# alpha=["a","b","c", "d", "e","f","g","h", "i", "j"]
# print(alpha[3:7])





#define a class
class bike: 
    name = ""
    gear =0
    
# create object of class
bike1 = bike()
#access attributes and assign new values
bike1.gaer = 11
bike1.name = "mountain bike"
print(f"name:{bike1.name}, gears: {bike1.gear}") 






class room:
    length =0.0
    breadth = 0.0
    #method to calculate area
    def calculate_area(self):
        print("area of room =", self.length * self.breadth)
study_room = room()
study_room.length = 42.5
study_room.breadth = 30.8
study_room.calculate_area()







class Employee:
    __id=0
    __name=""
    __gender=""
    __city=""
    __salary=0
    def setData(self):
        self.__id=int(input("Enter Id:\t"))
        self.__name = input("Enter Name:\t")
        self.__gender = input("Enter Gender:\t")
        self.__city = input("Enter City:\t")
        self.__salary = int(input("Enter Salary:\t"))
    def showData(self):
        print("Id\t\t:",self.__id)
        print("Name\t:", self.__name)
        print("Gender\t:", self.__gender)
        print("City\t:", self.__city)
        print("Salary\t:", self.__salary)


def main():
    #Employee Object
    emp=Employee()
    emp.setData()
    emp.showData()

if __name__=="__main__":
    main()





import csv
with open('test.csv', 'w', newline=  "") as file:
    writer = csv.writer(file)
    writer.writerow(["SN", "Movie", "Protagonist"])
    writer.writerow([1, "Lord of the Rings", "Frodo Baggins"])
    writer.writerow([2, "Harry Potter", "Harry Potter"])



f=open(‘new.txt','w')
f.write(“Bano Qabil Al-khidmat”)
f.close()
       
f=open(‘new.txt’)
print(f.read()))





f=open('first.txt', 'a')
f.write("  So practice it daily")
f=open('first.txt')
print(f.read())





step 1:		pip install virtualenv on cmd mode
step 2: 		create folder streamlit tut on desktop and copy path
step 3: 		cmd mode and streamlit tut folder run this command virtualenv streamlitenv
step 4:		cmd mode select script folder type activate
step 5:		show on cmd (streamlitenv) C:\Users\Ghuffi\Desktop\streamlit tut\streamlitenv\Scripts>
step 6:		pip install streamlit
step 7:		streamlit hello
step 8:		Local URL: http://localhost:8501
  		Network URL: http://192.168.0.112:8501

Run your Streamlit app.
		streamlit run app.py
If this doesn't work, use the long-form command:
		python -m streamlit run app.py





  # pip install sqlite3
import streamlit as st
import sqlite3

# Function to create a table if it doesn't exist
def create_table():
    conn = sqlite3.connect('example.db')
    c = conn.cursor()
    c.execute('''CREATE TABLE IF NOT EXISTS records
                 (id INTEGER PRIMARY KEY, name TEXT, age INTEGER)''')
    conn.commit()
    conn.close()

# Function to insert a record into the database
def insert_record(name, age):
    conn = sqlite3.connect('example.db')
    c = conn.cursor()
    c.execute('''INSERT INTO records (name, age) VALUES (?, ?)''', (name, age))
    conn.commit()
    conn.close()

# Function to display all records
def display_records():
    conn = sqlite3.connect('example.db')
    c = conn.cursor()
    c.execute('''SELECT * FROM records''')
    records = c.fetchall()
    conn.close()
    return records

# Function to delete a record from the database
def delete_record(record_id):
    conn = sqlite3.connect('example.db')
    c = conn.cursor()
    c.execute('''DELETE FROM records WHERE id = ?''', (record_id,))
    conn.commit()
    conn.close()

# Create table if not exists
create_table()

# Streamlit UI
st.title('Record Management App')

# Input fields for record
name = st.text_input('Enter Name')
age = st.number_input('Enter Age')

# Button to add record
if st.button('Add Record'):
    insert_record(name, age)
    st.success('Record Added Successfully!')

# Display all records
st.title('Records')
records = display_records()
for record in records:
    st.write(record)
    if st.button(f'Delete {record[1]}'):
        delete_record(record[0])
        st.success(f'Record ID {record[0]} Deleted Successfully!')





 import sqlite3

# Connect to the SQLite database
conn = sqlite3.connect('records.db')
cursor = conn.cursor()

# Create a table if it doesn't exist
cursor.execute('''CREATE TABLE IF NOT EXISTS records (
                    id INTEGER PRIMARY KEY,
                    name TEXT,
                    age INTEGER,
                    email TEXT
                )''')
conn.commit()

def add_record(name, age, email):
    cursor.execute('''INSERT INTO records (name, age, email) VALUES (?, ?, ?)''', (name, age, email))
    conn.commit()
    print("Record added successfully.")

def view_records():
    cursor.execute('''SELECT * FROM records''')
    records = cursor.fetchall()
    print("ID | Name | Age | Email")
    for record in records:
        print(record)

def remove_record(record_id):
    cursor.execute('''DELETE FROM records WHERE id = ?''', (record_id,))
    conn.commit()
    print("Record removed successfully.")

# Example usage
add_record("Asif Khan", 30, "asif@example.com")
add_record("Waseem zahid", 25, "waseem@example.com")
view_records()
remove_record(1)
view_records()

# Close the connection
conn.close()
