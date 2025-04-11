# Student-Database-System
1. Create the StudentDatabase class 2. Create the Student class 3. Initialize Student Object 4. Implement enroll_student() method 5. Implement drop_student() method 6. Implement view_student_info() method 7. Menu System 8. Error Handling 9. Data Privacy


class student_database:
    def __init__(self):
        self.students = []

  def __init__(self):
        self.students = []

  def add_student(self, student):
        self.students.append(student)

  def get_all_students(self):
        return self.students

  def find_student_by_id(self, student_id):
        for student in self.students:
            if student.get_student_id() == student_id:
                return student
        return None


student_database = student_database()


from studentDataBase import student_database

class student :

  def __init__(self , student_id , name , department , is_enrolled=False):
        self.__student_id = student_id
        self.__name = name
        self.__department = department
        self.__is_enrolled = is_enrolled
        student_database.add_student(self)


  def enroll_student(self):
        if self.__is_enrolled:
            print(f"student{self.student_id}is already enrolled") 
        else :
            self.__is_enrolled = True
            print(f"student{self.__student_id}has been enrolled")


    
   def drop_student(self):
         if not self.__is_enrolled:
            print(f"student{self.__student_id}is not currently enrolled")

   else:
            self.__is_enrolled = False
            print(f"student{self.__student_id}has been dropped")    
            

  def view_info(self):
        print("Student ID:", self.__student_id)
        print("Name:", self.__name)
        print("Department:", self.__department)
        print("Enrollment Status:", "Enrolled" if self.__is_enrolled else "Not Enrolled")
        print()

  def get_student_id(self):
        return self.__student_id 




        
from student import student
from studentDataBase import student_database

student("2413289", "Shadman Alvee", "CSE")
student("2426748", "Farhan Tanvir", "EEE")
student("2145534", "Muhtasim Fuad", "BBA")

def menu():
    while True:
        print("\n--- Student Management Menu ---")
        print("1. View All Students")
        print("2. Enroll Student")
        print("3. Drop Student")
        print("4. Exit")

  choice = input("Enter your choice: ")


  if choice == "1":
            students = student_database.get_all_students()
            if not students:
                print("No students found.")
            for student in students:
                student.view_info()

  elif choice == "2":
            student_id = input("Enter student ID to enroll: ")
            student = student_database.find_student_by_id(student_id)
            if student:
                student.enroll_student()
            else:
                print("Invalid student ID.")

  elif choice == "3":
            student_id = input("Enter student ID to drop: ")
            student = student_database.find_student_by_id(student_id)
            if student:
                student.drop_student()
            else:
                print("Invalid student ID.")

  elif choice == "4":
            print("Exiting program.")
            break

  else:
            print("Invalid choice. Please try again.")

menu()


        



