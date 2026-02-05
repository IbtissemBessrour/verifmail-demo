#verifmail
# Email Verifier Pro - Demo

Bienvenue sur la **démo du projet Email Verifier** !  
Cette application permet de vérifier rapidement si un email est valide, risqué ou invalide, et fournit un score et la raison.

🌐 **Testez l'application ici :** [https://verifmail.netlify.app](https://verifmail.netlify.app)

## Fonctionnalités principales

- Vérification des emails en masse
- Score de validité (0-100%)
- Catégorisation : ✅ Valide, ⚠ Risqué, ❌ Invalide
- Export CSV ou fichiers texte
- Mode clair / sombre

## Architecture

Le projet est composé de deux parties principales :

1. **Frontend (Angular)**  
   - Composants : EmailCheckComponent, AppComponent
   - Services : AppService pour connexion au backend
   - Envoyé vers Netlify pour l’hébergement
2. **Backend (Spring Boot)**  
   - Services : EmailService pour la vérification (format, DNS MX, SMTP)
   - API REST : `/api/email/check`
   - Hébergé sur Render (ou tout serveur Java) avec Docker

# Architecture du projet

         ┌───────────────┐
         │ Frontend      │
         │ Angular App   │
         │ Netlify       │
         └─────┬─────────┘
               │ HTTPS
               ▼
         ┌───────────────┐
         │ Backend       │
         │ Spring Boot   │
         │ Render        │
         └─────┬─────────┘
               │ SMTP/DNS
               ▼
         ┌───────────────┐
         │ Emails & MX   │
         │ vérification  │
         └───────────────┘

- Frontend : interface utilisateur pour entrer les emails et visualiser les résultats
- Backend : logique de vérification et calcul du score
- SMTP / MX : communication avec les serveurs mails pour tester l’existence
