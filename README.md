# Chkobba — .NET MAUI Android

Prototype de jeu local contre l'ordinateur, organisé pour accueillir ensuite un mode en ligne.

## Fonctionnalités
- Paquet tunisien de 40 cartes : quatre couleurs, valeurs de 1 à 10.
- Prise de cartes dont la somme correspond à la carte jouée.
- Pose d'une carte si aucune prise n'est choisie.
- Chkobba lorsque la table est vidée.
- Comptage indicatif des points majeurs en fin de partie.
- Icône MAUI dédiée et configuration Android alignée sur les autres applications du dépôt.

## Règles à valider
Les variantes tunisiennes diffèrent sur la distribution, les prises possibles et le comptage. Le moteur actuel utilise une règle simple de somme égale. Il faut confirmer ces choix avant de figer le jeu.

## Compiler en local
Depuis la racine du dépôt, avec le SDK .NET 10 et le workload Android MAUI :
```bash
dotnet workload install maui-android
dotnet publish ChkobbaMaui/ChkobbaMaui.csproj -f net10.0-android -c Release -p:AndroidPackageFormat=apk
```

Le workflow GitHub Actions `.github/workflows/android.yml` est configuré pour produire un APK et un AAB sur les commits de `main` ou manuellement depuis l'onglet Actions. Les fichiers sont publiés comme artefacts du workflow.

## Jeu en ligne
La prochaine étape proposée est une API ASP.NET Core avec SignalR, salons et matchmaking. Le serveur devra garder l'état officiel et valider chaque coup. Prévoir aussi reconnexion, invitations, abandon et protections anti-triche.
