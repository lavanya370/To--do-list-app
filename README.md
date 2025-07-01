todo_list = []  # This list stores all tasks

def show_menu():
    print("\n===== TO-DO LIST MENU =====")
    print("1. Show tasks")
    print("2. Add task")
    print("3. Remove task")
    print("4. Exit")

def show_tasks():
    if not todo_list:
        print("No tasks in your to-do list.")
    else:
        print("\nYour Tasks:")
        for index, task in enumerate(todo_list, start=1):
            print(f"{index}. {task}")

def add_task():
    task = input("Enter the task to add: ")
    todo_list.append(task)
    print(f'"{task}" has been added.')

def remove_task():
    show_tasks()
    if todo_list:
        try:
            task_no = int(input("Enter the task number to remove: "))
            removed = todo_list.pop(task_no - 1)
            print(f'"{removed}" has been removed.')
        except (IndexError, ValueError):
            print("Invalid task number.")

while True:
    show_menu()
    choice = input("Enter your choice (1-4): ")

    if choice == '1':
        show_tasks()
    elif choice == '2':
        add_task()
    elif choice == '3':
        remove_task()
    elif choice == '4':
        print("Exiting... Goodbye!")
        break
    else:
        print("Invalid choice. Please select from 1 to 4.")
