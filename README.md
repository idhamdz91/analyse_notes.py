# ==============================
# Projet : Analyse des notes des étudiants
# ==============================

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# 1. Génération des données
data = {
    "Nom": ["Ali", "Sofia", "Karim", "Leila", "Nadia", "Youssef", "Amel", "Omar"],
    "Âge": [20, 22, 21, 23, 20, 24, 22, 21],
    "Note": [15, 18, 12, 17, 14, 19, 16, 13]
}

# 2. Représentation des données sous forme de DataFrame
df = pd.DataFrame(data)
print("=== Jeu de données des étudiants ===")
print(df)

# 3. Analyse descriptive
print("\n=== Statistiques descriptives ===")
print(df.describe())

# Moyenne des notes
moyenne = df["Note"].mean()
print(f"\nMoyenne des notes : {moyenne:.2f}")

# Meilleure et plus faible note
max_note = df["Note"].max()
min_note = df["Note"].min()
print(f"Note maximale : {max_note}")
print(f"Note minimale : {min_note}")

# 4. Visualisation
plt.figure(figsize=(10,5))

# Histogramme des notes
plt.subplot(1,2,1)
sns.histplot(df["Note"], bins=5, kde=True, color="blue")
plt.title("Distribution des notes")

# Diagramme en barres par étudiant
plt.subplot(1,2,2)
sns.barplot(x="Nom", y="Note", data=df, palette="viridis")
plt.title("Notes des étudiants")

plt.tight_layout()
plt.show()
