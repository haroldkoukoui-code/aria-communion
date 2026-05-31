# Carte communion Aria

Site web d'invitation pour la première communion d'Aria Koukoui — 7 juin 2026.
URL cible : `aria-communion.netlify.app`

---

## Fichiers

| Fichier | Rôle |
|---------|------|
| `index.html` | Page d'invitation (mobile-first, tout-en-un) |
| `gallery.html` | Galerie photos post-événement (upload Supabase) |
| `assets/aria.jpg` | Photo d'Aria |

---

## Étape 1 — Configurer Supabase pour la galerie

1. Va sur [supabase.com](https://supabase.com) et ouvre ton projet
2. Crée un bucket de stockage nommé **`communion-aria`**
   - Aller dans **Storage > New bucket**
   - Nom : `communion-aria`
   - Cocher **Public bucket**
3. Récupère tes clés :
   - **Project URL** et **anon public key** dans Settings > API
4. Dans `gallery.html`, remplace ces deux lignes :
   ```js
   const SUPABASE_URL  = 'REMPLACER_PAR_TON_URL_SUPABASE';
   const SUPABASE_ANON = 'REMPLACER_PAR_TON_ANON_KEY';
   ```

---

## Étape 2 — Déployer sur Netlify via GitHub

### Créer le repo GitHub

```bash
cd livrables/sites-web/2026-05-carte-communion-aria
git init
git add .
git commit -m "feat: site invitation communion Aria"
gh repo create aria-communion --public --source=. --push
```

### Connecter Netlify

1. Va sur [app.netlify.com](https://app.netlify.com)
2. **Add new site > Import an existing project > GitHub**
3. Sélectionne le repo `aria-communion`
4. Build settings :
   - Build command : *(laisser vide)*
   - Publish directory : `.` (point)
5. Cliquer **Deploy site**
6. Dans **Site configuration > Site details**, changer le nom en `aria-communion`
   → URL finale : `aria-communion.netlify.app`

---

## Étape 3 — Tester

- Ouvrir `aria-communion.netlify.app` sur mobile
- Vérifier les liens Maps (église + excursion)
- Tester l'upload d'une photo dans la galerie
- Partager le lien par WhatsApp

---

## Partager par WhatsApp

Copier et envoyer ce message :

> Bonjour 🌸 Voici votre invitation pour la première communion d'Aria, le dimanche 7 juin.
> Tous les détails de la journée sont ici :
> https://aria-communion.netlify.app
