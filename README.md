# todo-project
System Programming and Administration project
### README - Gestionnaire de tâches `todo`

Le script `todo` est un gestionnaire de tâches simple en ligne de commande pour les systèmes Linux. Il permet de créer, mettre à jour, supprimer, afficher et rechercher des tâches. Chaque tâche a un identifiant unique, un titre, une description, un lieu, une date et une heure d'échéance, ainsi qu'un indicateur de complétion.

### Installation

1. **Téléchargez le script `todo` et placez-le dans un répertoire de votre choix**.
2. **Rendez le script exécutable** :
   ```bash
   chmod +x /chemin/vers/votre/script/todo
   ```
3. **Installez le script** :
   ```bash
   /chemin/vers/votre/script/todo install
   ```
   Cette commande copie le script dans `/usr/local/bin` et le rend accessible de partout.

### Utilisation

#### Afficher l'aide

Pour afficher l'aide et les instructions d'utilisation, exécutez :

```bash
todo help
```

#### Ajouter une nouvelle tâche

- **Création normale** :
  ```bash
  todo create -n
  ```
  Exemple de session :
  ```bash
  $ todo create -n
  Enter title (required): Acheter des fruits
  Enter description: Aller au marché pour acheter des fruits frais
  Enter location: Marché central
  Enter due date (DD-MM-YYYY, required): 25-05-2024
  Enter due time (HH:MM, optional): 10:00
  Task added successfully.
  ```

- **Création rapide** :
  ```bash
  todo create -r "Acheter des fruits" 25-05-2024
  ```
  Exemple de session :
  ```bash
  $ todo create -r "Acheter des fruits" 25-05-2024
  Task added successfully.
  ```

#### Mettre à jour une tâche existante

- **Marquer comme complète** :
  ```bash
  todo update -c <id>
  ```
  Exemple de session :
  ```bash
  $ todo update -c 1
  Task marked as completed.
  ```

- **Marquer comme incomplète** :
  ```bash
  todo update -i <id>
  ```
  Exemple de session :
  ```bash
  $ todo update -i 1
  Task marked as incomplete.
  ```

- **Modifier tous les champs** :
  ```bash
  todo update -a <id>
  ```
  Exemple de session :
  ```bash
  $ todo update -a 1
  Enter new title (leave empty to keep current): modif
  Enter new description (leave empty to keep current): desu dess
  Enter new location (leave empty to keep current): uir
  Enter new due date (DD-MM-YYYY, leave empty to keep current): 20-05-2024
  Enter new due time (HH:MM, leave empty to keep current): 18:08
  Is the task completed? (true/false, leave empty to keep current): true
  Task updated successfully.
  ```

- **Modifier des champs spécifiques** :
  ```bash
  todo update -n <id> [options]
  ```
  Options disponibles :
  - `-t` : Titre
  - `-d` : Description
  - `-l` : Lieu
  - `-dd` : Date d'échéance (DD-MM-YYYY)
  - `-dt` : Heure d'échéance (HH:MM)

  Exemple de session :
  ```bash
  $ todo update -n 1 -d "Changer la description" -dd 21-05-2024
  Task updated successfully.
  ```

#### Supprimer une tâche

```bash
todo delete <id>
```

Exemple de session :
```bash
$ todo delete 1
Task deleted successfully.
```

###Afficher les détails d'une tâche
```bash
todo show <id>
```
Exemple de session :

```bash
$ todo show 1
Task ID: 1
Title: modif
Description: desu dess
Location: uir
Due date and time: 20-05-2024 18:08
Completed: true
```

#### Lister les tâches d'un jour donné

```bash
todo -d 25-05-2024
```

Exemple de session :
```bash
$ todo -d 25-05-2024
Completed tasks on 25-05-2024:
No completed tasks found.

Uncompleted tasks on 25-05-2024:
ID: 1, Title: Acheter des fruits, Due date: 25-05-2024, Completed: false
```

#### Rechercher des tâches par titre

```bash
todo search -t "motclé"
```

Exemple de session :
```bash
$ todo search -t "modif"
Search results for title containing 'modif':
ID: 1, Title: modif, Due date: 20-05-2024, Completed: true
```

#### Rechercher des tâches par description

```bash
todo search -d "motclé"
```

Exemple de session :
```bash
$ todo search -d "desu"
Search results for description containing 'desu':
ID: 1, Title: modif, Due date: 20-05-2024, Completed: true
```

#### Afficher toutes les tâches

```bash
todo
```

Exemple de session :
```bash
$ todo
Completed tasks:
ID: 1, Title: modif, Due date: 20-05-2024, Completed: true

Uncompleted tasks:
ID: 2, Title: Acheter des fruits, Due date: 25-05-2024, Completed: false
```

#### Afficher les tâches du jour actuel

```bash
todo -t
```

Exemple de session :
```bash
$ todo -t
Completed tasks on 18-05-2024:
No completed tasks found.

Uncompleted tasks on 18-05-2024:
No uncompleted tasks found.
```
#
(ça a été écris par chatgpt-4o flemme d'écrire un REDME '-_- )
