# Cours HX4

## Association entre fichier LaTeX (`.tex`) et PDF (`.pdf`)

Pour qu'un PDF et un fichier LaTeX soient reconnus comme étant le **même cours**, la règle est très simple :

> **Ils doivent être dans le même dossier et avoir exactement le même nom (seule l'extension change).**

### Exemple :
```text
Mathématiques/chap01/
├── Sommes_produits_mpsi_ch01.tex   # Source LaTeX (prioritaire)
└── Sommes_produits_mpsi_ch01.pdf   # PDF associé (fallback)
```

---

## Fonctionnement lors de la publication

1. **Priorité au LaTeX** : Le script cherche le `.tex` et le compile en `.pdf` portant le même nom. Si la compilation réussit, ce nouveau PDF est publié sur le site.
2. **Fallback en cas d'erreur LaTeX** : Si la compilation échoue (erreur de syntaxe, package manquant, etc.), le script ne bloque pas le déploiement :
   - Il **conserve le `.pdf` de même nom** déjà présent sur GitHub.
   - S'il n'a pas exactement le même nom, il publie les autres `.pdf` trouvés dans ce même dossier de chapitre.
3. **Cours en PDF seul** : Si vous n'avez pas de fichier `.tex`, déposez simplement le `.pdf` dans le dossier voulu, il sera publié directement.
