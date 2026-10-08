# Chkobba — .NET MAUI Android

Prototype de jeu local contre l'ordinateur, organisé pour accueillir ensuite un mode en ligne.

## Fonctionnalités
- Paquet tunisien de 40 cartes : quatre couleurs, valeurs de 1 à 10.
- Prise de cartes dont la somme correspond à la carte jouée.
- Pose d'une carte si aucune prise n'est choisie.
- Chkobba lorsque la table est vidée.
- Comptage indicatif des points majeurs en fin de partie.

## À valider
Les variantes tunisiennes peuvent différer pour les prises multiples, la distribution et le comptage. Le moteur ci-joint utilise une règle simple de somme égale ; ces règles doivent être confirmées avant de publier une version définitive.

## Compilation
Installer le SDK .NET MAUI Android, puis lancer depuis le dossier du projet :
```bash
dotnet workload install maui-android
dotnet build -f net10.0-android
```

## Préparer le mode en ligne
Le plan proposé est une API ASP.NET Core avec SignalR, salons et matchmaking. Le serveur devra détenir l'état officiel et valider chaque coup. Prévoir aussi reconnexion, invitations, abandon et protections anti-triche.
