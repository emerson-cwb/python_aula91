# python_aula91
#Faça uma lista de comprar com listas O usuário deve ter a possibilidade de inserir, apagar e listar valores da sua lista Não permita que o programa quebre com  erros de índices #inexistentes na lista.

# Inicializa a lista de compras vazia
lista_de_compras = []

# Função para adicionar um item à lista de compras
def adicionar_item():
    item = input("Digite o item que deseja adicionar à lista: ")
    lista_de_compras.append(item)
    print(f"{item} foi adicionado à lista de compras.")

# Função para remover um item da lista de compras
def remover_item():
    if not lista_de_compras:
        print("A lista de compras está vazia. Não é possível remover itens.")
        return
    
    print("Itens na lista de compras:")
    for indice, item in enumerate(lista_de_compras):
        print(f"{indice + 1}: {item}")
    
    try:
        indice = int(input("Digite o número do item que deseja remover: ")) - 1
        if 0 <= indice < len(lista_de_compras):
            item_removido = lista_de_compras.pop(indice)
            print(f"{item_removido} foi removido da lista de compras.")
        else:
            print("Erro: Índice inválido. O item não pode ser removido.")
    except ValueError:
        print("Erro: Entrada inválida. Digite um número válido.")

# Função para listar os itens da lista de compras
def listar_itens():
    if lista_de_compras:
        print("Lista de Compras:")
        for indice, item in enumerate(lista_de_compras):
            print(f"{indice + 1}: {item}")
    else:
        print("A lista de compras está vazia.")

# Loop principal do programa
while True:
    print("\nOpções:")
    print("1: Adicionar item à lista")
    print("2: Remover item da lista")
    print("3: Listar itens da lista")
    print("4: Sair")

    escolha = input("Escolha uma opção (1/2/3/4): ")

    if escolha == '1':
        adicionar_item()
    elif escolha == '2':
        remover_item()
    elif escolha == '3':
        listar_itens()
    elif escolha == '4':
        break
    else:
        print("Escolha inválida. Por favor, escolha uma opção válida (1/2/3/4).")

print("Programa encerrado.")
