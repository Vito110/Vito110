class Employee:
    data = 0

    def __init__(self, inp, out):
        self.inp = inp
        self.out = out

    def list_employee(self):
        with open(self.inp, "r") as file:
            text = file.read().split('\n')
            
            for i in range(len(text)):
                self.data = text
                data = text[i].split(',')
                
                print("##############################")
                print(f'Personal number: {data[0]}')
                print(f'Username: {data[1]}')
                print(f'Name: {data[2]}')
                print(f'Surname: {data[3]}')
                print(f'Employment start: {data[4]}')
                
                with open(self.out, "w") as file1:
                    for i in range(len(text)):
                        data = text[i].split(',')
                        file1.write("##############################\n")
                        file1.write(f'Personal number: {data[0]}\n')
                        file1.write(f'Username: {data[1]}\n')
                        file1.write(f'Name: {data[2]}\n')
                        file1.write(f'Surname: {data[3]}\n')
                        file1.write(f'Employment start: {data[4]}\n')

    def count_employee(self):
        print(len(self.data))

    def new_employee(self):
        with open(self.out, "a") as file1:
            file1.write("##############################\n")
            file1.write(f'Personal number: {input("Personal number: ")}\n')
            file1.write(f'Username: {input("Username: ")}\n')
            file1.write(f'Name: {input("Name: ")}\n')
            file1.write(f'Surname: {input("Surname: ")}\n')
            file1.write(f'Employment start: {input("Employment start: ")}\n')


emp1 = Employee("input.txt", "output.txt")
emp1.list_employee()
emp1.count_employee()

while True:
    choice = input(
        "What do you want to do? \nAdd employee Y: \nEnd task N: ")
    if choice.upper() == "Y":
        emp1.new_employee()
    else:
        quit()
