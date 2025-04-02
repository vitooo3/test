# Istruzioni per la creazione di un repository Git con due branch

Questo documento contiene le istruzioni dettagliate per completare il compito di creazione di un repository Git con due branch (main e prova) e il push su GitHub.

## Prerequisiti

- Git installato sul computer
- Un account GitHub
- Un repository GitHub già creato (in questo caso: https://github.com/vitooo3/test.git)

## Passaggi da seguire

### 1. Inizializzazione del repository Git locale

```bash
# Crea una cartella per il progetto
mkdir git_progetto
cd git_progetto

# Inizializza il repository Git
git init

# Rinomina il branch predefinito da master a main
git branch -m master main
```

### 2. Creazione dei file nel branch main

```bash
# Assicurati di essere nel branch main
git checkout main

# Crea il file README.md
cat > README.md << 'EOF'
# Progetto Git

Questo è un repository di esempio con due branch:
- main: contiene README.md, progetto.txt e provafinale.txt
- prova: contiene provat.txt e schema.txt
EOF

# Crea il file progetto.txt
cat > progetto.txt << 'EOF'
Questo è il file progetto.txt nel branch main.
Contiene informazioni sul progetto di esempio per Git.
EOF

# Crea il file provafinale.txt
cat > provafinale.txt << 'EOF'
Questo è il file provafinale.txt nel branch main.
Contiene informazioni sulla prova finale del progetto Git.
EOF

# Aggiungi i file al staging area
git add README.md progetto.txt provafinale.txt

# Configura l'identità Git (se non l'hai già fatto)
git config --global user.email "tuo-email@esempio.com"
git config --global user.name "Tuo Nome"

# Esegui il commit dei file
git commit -m "Aggiunti i file nel branch main"
```

### 3. Creazione del branch prova e dei suoi file

```bash
# Crea il branch prova e passa ad esso
git checkout -b prova

# Crea il file provat.txt
cat > provat.txt << 'EOF'
Questo è il file provat.txt nel branch prova.
Contiene informazioni di test per il branch prova del progetto Git.
EOF

# Crea il file schema.txt
cat > schema.txt << 'EOF'
Questo è il file schema.txt nel branch prova.
Contiene lo schema di progettazione per il progetto Git di esempio.
EOF

# Aggiungi i file al staging area
git add provat.txt schema.txt

# Esegui il commit dei file
git commit -m "Aggiunti i file nel branch prova"
```

### 4. Configurazione del remote GitHub e push

```bash
# Aggiungi il remote GitHub
git remote add origin https://github.com/vitooo3/test.git

# Push del branch main
git checkout main
git push -u origin main

# Push del branch prova
git checkout prova
git push -u origin prova
```

### 5. Verifica del risultato

Dopo aver eseguito tutti i passaggi, dovresti avere:

1. Un repository Git locale con due branch:
   - `main`: contiene README.md, progetto.txt e provafinale.txt
   - `prova`: contiene provat.txt e schema.txt

2. Un repository GitHub con gli stessi due branch e file

Puoi verificare la struttura del repository su GitHub visitando:
- https://github.com/vitooo3/test/tree/main
- https://github.com/vitooo3/test/tree/prova

## Comandi utili per la verifica

```bash
# Visualizza tutti i branch
git branch

# Visualizza lo stato del repository
git status

# Visualizza la cronologia dei commit
git log --oneline --graph --all

# Visualizza i remote configurati
git remote -v
```

## Nota importante

Durante il push su GitHub, ti verrà richiesto di inserire le tue credenziali GitHub. Se hai abilitato l'autenticazione a due fattori, dovrai utilizzare un token di accesso personale invece della password. Puoi generare un token di accesso personale nelle impostazioni del tuo account GitHub.
