# Student-Registration-Tool

#Student Rgistration Tool

import csv

def write_into_csv(info_list):
    with open ('Student_Info.csv', 'a', newline='') as csv_file:
        writer = csv.writer(csv_file)
        if csv_file.tell()==0:
            writer.writerow(["Student Id", "Name", "DOB", "Department", "Contact Number", "E-Mail"])

        writer.writerow(info_list)
if __name__ == '__main__':
    condition = True
    student_num = 1

    #Logic

    while (condition):

        Student_Info = input(" Enter the information for student # {} in the Following format: (Id, Name, DOB, Department, Contact Number, E-Mail) ".format(student_num))

        #Using Split Function
        Student_Info_list = Student_Info.split(' ')
        print("\n The Entered Information is : \n Student Id:{} \n Name:{} \n DOB: {} \n Department: {} \n Contact Number: {} \n E-Mail: {}"
                .format(Student_Info_list[0], Student_Info_list[1], Student_Info_list[2], Student_Info_list[3], Student_Info_list[4], Student_Info_list[5]))


        write_into_csv(Student_Info_list)

        choice = input(" Do you like to Enter more Entries? (yes/no): ")
        print("\n")

        if choice == "yes":
            condition = True
            student_num = student_num + 1

        elif choice == "no":
            condition = False

print("\n")
