while True:
    user_action= input("Type add, show, edit or exit: ")
    user_action= user_action.strip()

    match user_action:
        case'add':
            todo= input("enter a todo: ") +"\n"

            file=open('todo.txt', 'r')
            todos= file.readlines()
            file.close()

            todos.append(todo)

            file = open('todo.txt', 'w')
            file.writelines(todos)
            file.close()
        case 'show':
             for item in todos:
                 print(item)
        case'edit':
             number= int(input("Number of the todo to edit:"))
             number= number- 1
             new_todo= input("Enter new todo: ")
             todos[number]= new_todo
        case 'exit':
             break

print("Bye!")
