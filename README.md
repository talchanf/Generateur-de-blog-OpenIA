# Générateur de blog avec l'API OpenAI

Petit script Python en ligne de commande qui génère un paragraphe de blog sur le sujet de ton choix, en appelant l'API d'OpenAI.

## Fonctionnement

1. Le programme demande si tu veux écrire un paragraphe (`Y` pour oui).
2. Tu saisis le sujet du paragraphe.
3. Le script envoie une requête à l'API OpenAI et affiche le texte généré.
4. Il recommence jusqu'à ce que tu répondes autre chose que `Y`.

Paramètres utilisés dans `blog_generator.py` :

| Paramètre | Valeur |
|---|---|
| Modèle | `gpt-3.5-turbo-instruct` |
| Longueur maximale | 400 tokens |
| Température | 0.3 (texte plutôt sobre et peu aléatoire) |
| Consigne envoyée | `Write a paragraph about the following topic.` suivie du sujet |

## Technologies

Python, API OpenAI (bibliothèque `openai`), `python-dotenv` pour charger la clé depuis un fichier `.env`.

## Lancer le projet

1. Cloner le dépôt puis installer les dépendances :
   ```
   pip install -r requirements.txt
   ```
2. Créer une clé sur [platform.openai.com](https://platform.openai.com/api-keys). L'API est payante à l'usage.
3. Créer un fichier `.env` à la racine du projet, avec ta clé :
   ```
   API_KEY=ta_cle_ici
   ```
   Ce fichier ne doit jamais être publié : il est exclu du dépôt par le `.gitignore`.
4. Lancer le script :
   ```
   python blog_generator.py
   ```

## Exemple d'utilisation

```
Write a paragraph? Y for yes, anything else for no. Y
What should this paragraph talk about? the benefits of learning to code
...paragraphe généré...
```

## Limites et pistes d'amélioration

- Le script produit un seul paragraphe à la fois, sans article complet ni plan.
- Les messages et la consigne envoyée à l'API sont en anglais, donc les textes générés le sont aussi par défaut.
- Aucune gestion des erreurs (clé invalide, quota dépassé, pas de connexion).
- Idées pour la suite : générer un article structuré (titre, introduction, sections), choisir la langue, enregistrer le résultat dans un fichier, passer à un modèle de chat plus récent.

## Contexte

Projet personnel pour découvrir l'utilisation d'une API d'intelligence artificielle depuis Python.
