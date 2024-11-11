import random

def introdução():
    print("Bem vindo ao mundo de A Fúria das Profundezas.")
    print("A história se passa em um tempo medieval,onde os personagens principais são um lenhador e seus dois filhos que vivem próximos do vilarejo Pedra Fina. O vilarejo está sendo constantemente atacado pelos monstros que vivem na caverna próxima a cidade, e sua missão é acabar com essa ameaça...")




players =[
    {"nome1":"Jhonny Lenhador","vida":35,"ataque":25},
    {"nome2":"Isaac Tijolinho","vida":25,"ataque":20},
    {"nome3":"Pomodoro Vareta","vida":25,"ataque":15}

]

inimigo= [ 
    {"nome1":"Balerion,o Dragão", "vida":70,"ataque":30},
    {"nome2":"Carlos, o Ork","vida":35,"ataque":26},
    {"nome3":"Urso Peba","vida":20,"ataque":17} 

]

def escolha_persongem(): 
    print("Escolha seu persongem:") 
    for i, p in enumerate(players):
        print(f"{i + 1} - {p}")
    player = players
    while True:
        escolha_persongem = input("digite o numero do player escolhido: ")
        if escolha_persongem.isdigit() and 1 <= int(escolha_persongem) <= len(players):
            player_escolhido = player[int(escolha_persongem)- 1]
            return player_escolhido
        else:
            print("opção inválida")
            
def batalha(player_escolhido, inimigo):
    print(f"Você encontrou o {inimigo["nome3"]}.")
    eai = input("O que você vai fazer?  (atacar/fugir)")
    if eai == "atacar":
            while player_escolhido["vida"] >= inimigo["nome3","ataque"] or inimigo["vida"] >= player_escolhido["ataque"]:
                continue
            if player_escolhido["vida"] <= inimigo["nome3","ataque"]:
                return "Você perdeu"
            elif inimigo["vida"] <= player_escolhido["ataque"]:
                return "Você ganhou"
            else:
                return "Empate"
            
itens = [
    {"item1":"Espada antiga": "+":10},
    {"item2":"Barril de ouro"},
    {"item3":"Carta misteriosa": "Volte! Você NÃO pode vencer aquela criatura... todos morreram e você será o próximo se for até lá."}
]

inventario = []
        
def caminhos(player_escolhido,inimigo):
    print("Você entrou na caverna e achou alguns caminhos para seguir...")
    caminho =input("Qual caminho você quer seguir?  (esquerda/direita/seguir em frente)")
    if caminho == "esquerda":
        print("Você entrou entrou na toca do Urso Peba, agora terá que enfrentar ele...")
        if inimigo["vida"] < 0:
            item_encontrado = "Barril de ouro"
            inventario.append(item_encontrado)
            print(f"Você recebeu {itens["item2"]}")
    elif caminho == "direita":
        print("Você encontrou Carlos,o Ork")
        if inimigo["vida"] < 0:
            item_encontrado = "Espada Antiga"
            inventario.append(item_encontrado)
            print(f"Você recebeu {itens["item1"]}")
            player_escolhido["ataque"] += 10
    elif caminho == "seguir em frente":
        print("siga sua jornada")
    else:
        print("opção inválida")
    
def jogar():
    introdução()
    players = escolha_persongem()
    caminhos()
    
