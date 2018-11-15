# projeto_udacity
Projeto Udacity


    
    frases_lacunas_respostas = {
    'facil': {
        'frase': 'Para __1__ entendedor, __2__ palavra __3__',
        'lacuna': ['__1__', '__2__', '__3__'],
        'resposta':['bom', 'meia', 'basta']
        },

    'medio' : {
        'frase': 'Água __1__, pedra __2__, tanto __3__ até que fura',
        'lacuna': ['__1__', '__2__', '__3__'],
        'resposta':['mole', 'dura', 'bate']
        },

    'dificil' : {
        'frase': 'O que os __1__ não veem, o __2__ não __3__',
        'lacuna': ['__1__', '__2__', '__3__'],
        'resposta':['olhos', 'coração', 'sente']
        }
    }

def mostra_boas_vindas():
    #EXIBE MENSAGEM DE BOAS VINDAS
    print ('Bem vindo ao jogo!!!')

def pergunta_dificuldade():
    #PERGUNTA A DIFICULDADE PARA O USUÁRIO
    #RETURN: (string)dificuldade 'fácil', 'médio', 'dificil'.
    dificuldades_validas = ['facil', 'medio', 'dificil']
    dificuldade = input('selecione a dificuldade (facil, medio ou dificil):\n').lower()
    while dificuldade not in dificuldades_validas:
        dificuldade = input('Opção invalida, tente novamente')

    print ("Voce selecionou o nivel " + dificuldade + ", vamos la!")
    return dificuldade


def obtem_frase_dificuldade(dificuldade):
    frase = frases_lacunas_respostas[dificuldade]['frase']
    lacunas = frases_lacunas_respostas[dificuldade]['lacuna']
    respostas = frases_lacunas_respostas[dificuldade]['resposta']
    return frase, lacunas, respostas

def pergunta_resposta_lacuna(lacuna, resposta):
    resposta_usuario = input('Digite o valor da lacuna' + lacuna + ':\n').lower()
    while resposta_usuario != resposta:
        resposta_usuario = input('Sua resposta esta errada, tente novamente:\n').lower()
    print ('Voce acertou!\n')
    return resposta_usuario

def substitui_lacuna_por_resposta(frase, lacuna, resposta):
    return frase.replace(lacuna, resposta)
def mostrar_parabens_final(frase):
    print (frase + '\nParabens, voce conseguiu!!')



#esqueleto do programa
def inicia_jogo():
    mostra_boas_vindas()
    dificuldade = pergunta_dificuldade()
    frase, lacuna, resposta = obtem_frase_dificuldade(dificuldade)
    for index, lacuna in enumerate(lacuna):
      print ("A frase é: " + frase)
      resposta_usuario = pergunta_resposta_lacuna(lacuna, resposta[index])
      frase = substitui_lacuna_por_resposta(frase, lacuna, resposta_usuario)
    mostrar_parabens_final(frase)

inicia_jogo()
