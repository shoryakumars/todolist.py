# todolist.py

class ToDoList:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)
        print("Task were added : ",task)

    def remove_task(self,task_index):
        if 0 <= task_index < len(self.tasks):
            removed_task = self.tasks.pop(task_index)
            print("Task were removed successfully : ",removed_task)
        else:
            print("Invalid task index")
    
    
    def display(self):
        if not self.tasks:
            print("There is no tasks in the list")
        else:
            print("Tasks : ")
            for index, task in enumerate(self.tasks):
                print(f"{index + 1}. {task}")


def main():
    todo_list = ToDoList()

    while True:
        print("\nMenu:\n1. Add Task\n2. Remove Tasks\n3. Display Tasks\n4. Quit")

        choice = input("Enter your choice : ")

        if choice == '1':
            task = input("Enter your task : ")
            todo_list.add_task(task)
        elif choice == '2':
            task_index = int(input("Enter your Task index to remove : ")) - 1
            todo_list.remove_task(task_index)
        elif choice == '3':
            todo_list.display_tasks()
        elif choice == '4':
            print("Good byee!")
            break
        else:
            print("Invalid choice....\nPlease choice correct option....")

if __name__ == "__main__":
    main()


            
