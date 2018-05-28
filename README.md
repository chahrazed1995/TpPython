# TpPython
# -*- coding: utf-8 -*-
import os
import pickle
from random import choice
from fichier sauvergarde import *
from random import*
 
def menu(rejouer):
    fin=False
    while fin==False: # S'écrit 'while not fin:'
         print("\n\n******** Menu ********")            #  \n = sauter une ligne
         print("Bienvenue dans le jeu de Nim!")
         print("Le but du jeu est simple : Choisir un nombre de tas (entre 3 et 7) puis tirer autant de tas un nombre de pierres (entre 5 et 23 ) .\n A son tour, le deuxièmre joueur  en fera de meme et ainsi de suite jusqu'a ce qu'il n'y ait plus de pierres.\n Le perdant est celui qui retirera la derniere pierre.")
         print("(1) Jouer ")
         print("(2) Quitter le programme ")
          if rejouer==1
              print("Donner le nom du joueur")
              nom=input(" le joueur est :")
            
          else 
             if rejouer==2:
            
            fin=True
 
         return rejouer # !! 'rejouer' est donné en argument à la fonction,
                        # quelle était ton intention ?
    
def nom_joueur():

    #Fonction chargée de récupérer le nom de l'utilisateur.

    #Si ce nom existe déjà, on appelle récursivement la fonction pour en obtenir un nouveau


    joueur = input("Tapez le nom: ")

    if not joueur.isalnum() :
        print("Ce nom existe deja")
        # On appelle de nouveau la fonction pour avoir un autre nom
        return nom_joueur()

    else:

        return nom_utilisateur
def PartieJoueur(nbrtas,nbrpierpartas,nbrpierAretirer,reponse): # A quoi sert l'argument 'reponse' ?
    print("/"*nbrpierpartas,end='') 
    print("Vous jouez avec",tasaffiche,"tas")
    print(" Vous jouez avec",pieraffiche,"pierres") 
    
    def recup_scores():

    #Cette fonction récupère les scores enregistrés si le fichier existe.
    #Dans tous les cas, on renvoie un dictionnaire, 
    #soit l'objet dépicklé.
    #On s'appuie sur nom_fichier_scores défini dans fichier sauvegarde.py"""

    if os.path.exists(nom_fichier_scores): # Le fichier existe
        # On le récupère
        fichier_scores = open(fichier_scores, "rb")
        mon_depickler = pickle.Unpickler(fichier_scores)
        scores = mon_depickler.load()
        fichier_scores.close()
    else: # Le fichier n'existe pas

        scores = {}

    return scores

def meilleur_score (nbcoup)
coup = int(nbcoup/2) #nbcoup calcule le nbr de coup des deux joueurs or coup calcule le nbr de coup pour chaque joueur
for j in range (coup)
    score = sum (j * (10)^j)
    
def enregistrer_scores(scores):

    #Cette fonction se charge d'enregistrer les scores dans le fichier

    #nom_fichier_scores. Elle reçoit en paramètre le dictionnaire des scores à enregistrerr
    fichier_scores = open(fichier_scores.score, "wb") 
    # On écrase les anciens scores

    mon_pickler = pickle.Pickler(fichier_scores.score)

    mon_pickler.dump(scores)

    fichier_scores.close()
    
    # C'est ici qu'il faudrait saisir le nombre de pierres choisi par le joueur
    while 1:
        if (nbrpierAretirer<5):
            print("Entrer un nombre SUPERIEUR ou egal a 5 ")
            # Ici, on dit au joueur de rectifier son choix ...
            reponse = False
        elif (nbrpierAretirer>5):
            print("Entrer un nombre INFERIEUR ou egal 23")
            # .. ici encore ...
            reponse = False
        # ... sans lui donner la possibilité de le faire.
        if reponse == True: #
            break
 
            # !! Les lignes qui suivent ne s'exécuteront jamais',
            # est-ce le but ? !!
            print("/"*pieraffiche,end='')  # Tâche ménagère, ne devrait pas être ici.
            if(pieraffiche<=1):
                print(" Vous avez gagne :D")
            
 
#Programme principal #
rejouer=1
menu(rejouer)
rejouer=input("Quel est votre choix? : ") # Devrait être retourné par la fonction menu()
nbrtas=int(input("Rentrer le nombre de tas"))
nbrpier=int(input("Rentrer un nombre entier de pierres : "))# >> fonction menu()

for i in range(1,2) #Afficher les données de chaque joueur 
    a=nom_joueur()   
          print('a')
        x=open('fichier sauvergarde.py','w')
    
        for i in range(nbrtas) 
            pieraffiche=nbrpier
             print(pieraffiche)
            
# Mettre ceci dans une fonction
nbcoup=1

for i range(1,2)
    
    print("Le tour du joueur")
    print(i)
    tasaffiche=int(input("Donner le tas choisi"))
    nbrpierAretirer=int(input("Combien de pierres voulez-vous retirer? : "))
        reponse = True
            PartieJoueur(nbrtas,nbrpierpartas,nbrpier,nbrpierAretirer,reponse)
                nbrpierAretirer = (int(random()*23+5)) 
                pieraffiche=pieraffiche-nbrpierAretirer
                nbcoup==nbcoup+1
                utilisateur=nom_joueur()
    if not nom_joueur #affaceter au joueur gagnant le meilleur score et l'enregistrer sur le fichier 
     score = meilleur_score()
        enregister_scores(score)
        
while rejouer:
    nbrpier=int(input("Rentrer un nombre entier de pierres : "))
    pieraffiche=nbrpier
    while pieraffiche>5: 
        # !!! Boucle infinie s'il reste plus de pierre !!!
        print("/"*nbrpier,end='')
        print(" Vous jouez avec",pieraffiche,"pierres")
        score = 0
 
    rejouer = menu() # !! menu() demande un argument
 
# Fin du programme #
print("*** Fin ***")
