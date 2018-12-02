# projeto_udacity
Projeto Udacity

def boas_vindas():
  print ("Bem vindo ao jogo!!")
#___________________________________________________________________

def pergunta_nivel():
  validos = ['facil', 'medio', 'dificil']
  resposta_dificuldade = input ('Selecione o nivel(facil, medio, dificil)\n')
  while resposta_dificuldade not in validos:
    resposta_dificuldade = input ('Sua resposta esta incorreta, tente novamente.\n')
  print ('Você selecionou o nível ' +resposta_dificuldade+ ' vamos lá!!!')
  return resposta_dificuldade
#_____________________________________________________________________

frase_facil = "Água __1__ pedra __2__, tanto bate até que __3__."
resposta_facil = ["mole", "dura", "fura"]

frase_medio = "Em __1__ de __2__ quem tem __3__ é rei."
resposta_medio = ["terra", "cego", "olho"]

frase_dificil = "Melhor um __1__ na __2__ do que dois __3__."
resposta_dificil = ["pássaro", "mão", "voando"]

lacunas = ["__1__", "__2__", "__3__"]


def frase_lacuna_resposta(nivel):
  if nivel == 'facil':
    return (frase_facil, resposta_facil, lacunas)
  elif nivel == 'medio':
    return (frase_medio, resposta_medio, lacunas)
  elif nivel == 'dificil':
    return (frase_dificil, resposta_dificil, lacunas) 
#____________________________________________________________________

def resposta_usuario1(frase, lacuna, resposta, indice):
  resposta1 = input ("Qual é o valor da lacuna __" +str(indice)+ "__?")
  while resposta1 != resposta[indice-1]:
    print ("A resposta está incorreta, tente novamente.")
    resposta1 = input ("Qual o valor da coluna __" +str(indice)+ "__?")
  print ("Parabéns, você acertou!!!")
  print (frase.replace("__"+str(indice)+"__", resposta1)) 
  frase = (frase.replace("__"+str(indice)+"__", resposta1))
  return frase
#____________________________________________________________________

def inicia_jogo():
  boas_vindas()
  nivel = pergunta_nivel()
  frase, resposta, lacuna = frase_lacuna_resposta(nivel)
  print ("A frase desafio é: " +frase)
  for indice in range(1, 4):
    frase = resposta_usuario1(frase, lacuna, resposta, indice)
  print ("Parabéns, você concluiu o nível " +nivel+ "!!!")
    
inicia_jogo() 


    
    
