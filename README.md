
def main():
    tasks = []

    while True:
        print("\nTo-Do List Application")
        print("1. Add Task")
        print("2. Mark Task as Completed")
        print("3. View Tasks")
        print("4. Delete Task")
        print("5. Exit")
        choice = input("Enter your choice: ")

        if not choice.isdigit():
            print("Invalid input. Please enter a number between 1 and 5.")
            continue

        choice = int(choice)

        if choice == 1:
            task = input("Enter task: ").strip()
            if not task:
                print("Task cannot be empty.")
            else:
                tasks.append(task)
                print("Task added successfully.")

        elif choice == 2:
            if not tasks:
                print("No tasks to mark as completed.")
                continue
            try:
                task_number = int(input("Enter task number to mark as completed: "))
                if 1 <= task_number <= len(tasks):
                    print(f"Task '{tasks[task_number - 1]}' marked as completed.")
                    tasks.pop(task_number - 1)
                else:
                    print("Invalid task number.")
            except ValueError:
                print("Invalid input. Please enter a valid task number.")

        elif choice == 3:
            if not tasks:
                print("No tasks available.")
            else:
                print("Tasks:")
                for i, task in enumerate(tasks, start=1):
                    print(f"{i}. {task}")

        elif choice == 4:
            if not tasks:
                print("No tasks to delete.")
                continue
            try:
                task_number = int(input("Enter task number to delete: "))
                if 1 <= task_number <= len(tasks):
                    print(f"Task '{tasks[task_number - 1]}' deleted.")
                    tasks.pop(task_number - 1)
                else:
                    print("Invalid task number.")
            except ValueError:
                print("Invalid input. Please enter a valid task number.")

        elif choice == 5:
            print("Exiting...")
            break

        else:
            print("Invalid choice. Please select a number between 1 and 5.")

if __name__ == "__main__":
    main()
