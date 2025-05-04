# Sistema simples de Gerenciador de Tarefas

tarefas = []

def adicionar_tarefa(tarefa):
    tarefas.append(tarefa)
    print(f"Tarefa '{tarefa}' adicionada com sucesso.")

def listar_tarefas():
    if not tarefas:
        print("Nenhuma tarefa registrada.")
    else:
        print("\nLista de Tarefas:")
        for idx, tarefa in enumerate(tarefas, start=1):
            print(f"{idx}. {tarefa}")
        print()

def remover_tarefa(numero):
    if 1 <= numero <= len(tarefas):
        removida = tarefas.pop(numero - 1)
        print(f"Tarefa '{removida}' removida com sucesso.")
    else:
        print("Número de tarefa inválido.")

def menu():
    while True:
        print("\n--- Gerenciador de Tarefas ---")
        print("1. Adicionar Tarefa")
        print("2. Listar Tarefas")
        print("3. Remover Tarefa")
        print("4. Sair")

        opcao = input("Escolha uma opção: ")

        if opcao == "1":
            tarefa = input("Digite a tarefa: ")
            adicionar_tarefa(tarefa)
        elif opcao == "2":
            listar_tarefas()
        elif opcao == "3":
            listar_tarefas()
            try:
                numero = int(input("Digite o número da tarefa a remover: "))
                remover_tarefa(numero)
            except ValueError:
                print("Por favor, digite um número válido.")
        elif opcao == "4":
            print("Saindo do sistema.")
            break
        else:
            print("Opção inválida. Tente novamente.")

# Executar o menu
menu()
# cyber
