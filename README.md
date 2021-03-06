# YrFight
Jeu 2D en réseau de combat réalisé avec le langage Ymir

## Cahier des charges

### Gameplay

 - Jeu de combat en 2D et en réseau, 2 joueurs
 - Jouable avec le clavier ou une manette
 - Chaque joueur a une barre de vie, frapper l'autre joueur lui retire de la vie, le premier qui n'a plus de vie a perdu
 - Le joueur peut utiliser des coups simples / ou peut utiliser des combos
 
### Visuellement...

 - 3 écrans :
   - choix du perso : l'utilisateur clique sur l'image de perso qui l'intéresse
   - configuration des touches
   - écran du jeu
   
 - Utilisation des sprites :
   - descriptions dans un fichier json (extension .sprt)
   - Interface (GUI)  de création de sprite afin de faciliter la création du .sprt
   
### Réseau

 - un serveur et un client
 - création d'une petite lib style netez afin de communiquer par messages

### Format du fichier sprite (.sprt)

```
[
  {
    sprites: [
      {      
        id: '{{string()}}',
        position: '{{integer(20, 40)}}, {{integer(20, 40)}}',
        width: '{{integer(20, 40)}}',
        height: '{{integer(20, 40)}}',
        hitboxes: [
          {
            position: '{{integer(20, 40)}}, {{integer(20, 40)}}',
            width: '{{integer(20, 40)}}',
            height: '{{integer(20, 40)}}'
          }
        ]
      }
    ],
    animations: [
      {
        id: '{{string()}}',
        frames: [
          {
            spriteId : '{{objectId()}}',
            delayBefore: '{{integer(20, 40)}}'
          }
        ],
        canLoop: '{{bool()}}'
      }
    ]
  }
]
```
