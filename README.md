# To-Do-List-in-Python
tasks = []

def show_tasks():
    if not tasks:
        print("\n📋 No tasks added yet.\n")
    else:
        print("\n📝 To-Do List:")
        for i, task in enumerate(tasks, start=1):
            status = "✅" if task["completed"] else "❌"
            print(f"{i}. {status} {task['task']}")
    print()

def add_task():
    task = input("Enter task: ").strip()
    if task:
        tasks.append({"task": task, "completed": False})
        print("Task added successfully!\n")
    else:
        print("Task cannot be empty!\n")

def mark_complete():
    show_tasks()
    try:
        index = int(input("Enter task number to mark as complete: ")) - 1
        tasks[index]["completed"] = True
        print("Task marked as complete!\n")
    except:
        print("Invalid task number!\n")

def mark_incomplete():
    show_tasks()
    try:
        index = int(input("Enter task number to mark as incomplete: ")) - 1
        tasks[index]["completed"] = False
        print("Task marked as incomplete!\n")
    except:
        print("Invalid task number!\n")

def delete_task():
    show_tasks()
    try:
        index = int(input("Enter task number to delete: ")) - 1
        deleted = tasks.pop(index)
        print(f"Deleted: {deleted['task']}\n")
    except:
        print("Invalid task number!\n")

def main():
    while True:
        print("===== TO-DO LIST MENU =====")
        print("1. Show Tasks")
        print("2. Add Task")
        print("3. Mark Complete")
        print("4. Mark Incomplete")
        print("5. Delete Task")
        print("6. Exit")

        choice = input("Choose an option (1-6): ").strip()

        if choice == '1':
            show_tasks()
        elif choice == '2':
            add_task()
        elif choice == '3':
            mark_complete()
        elif choice == '4':
            mark_incomplete()
        elif choice == '5':
            delete_task()
        elif choice == '6':
            print("Goodbye! 👋")
            break
        else:
            print("Invalid choice! Try again.\n")

if __name__ == "__main__":
    main()
