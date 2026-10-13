# CORBÉ 44 — Signature mobile

Complément Outlook destiné à insérer automatiquement la signature CORBÉ 44 lors de la création d'un nouveau message sur Outlook mobile.

## Fichiers
- `manifest.xml` : manifeste du complément CORBÉ 44, identifiant propre au complément.
- `mobile.html` et `mobile.js` : page et script utilisés par Outlook.
- `auth.html` : URI de redirection déclarée pour l'authentification Microsoft Entra (SPA).

## Paramètres d'identité Entra présents dans le code
- Application : `CORBE44-Signature-Mobile`
- Client ID : `4e53fe58-6711-4d92-b141-c90f8ca3b550`
- Tenant ID : `63fb9113-5dd8-452e-9c0b-279a1e9170cc`
- URI de redirection SPA attendue : `https://xaviouk.github.io/corbe44-signature-mobile/auth.html`
- Permission Microsoft Graph utilisée par le code : permission déléguée `User.Read`.

## Avant le déploiement dans le tenant CORBE44
1. Dans Entra ID > Inscriptions d'applications, ouvrir `CORBE44-Signature-Mobile` et vérifier que le Client ID et le Tenant ID correspondent aux valeurs ci-dessus.
2. Dans Authentification, vérifier que l'URI `https://xaviouk.github.io/corbe44-signature-mobile/auth.html` est enregistrée sous la plateforme **Application monopage (SPA)**.
3. Dans Autorisations API, vérifier Microsoft Graph > `User.Read` de type **déléguée**. N'ajouter aucune autorisation d'écriture ni aucun accès à d'autres utilisateurs : le code lit uniquement le profil de l'utilisateur connecté via `/me`.
4. Vérifier les politiques de consentement utilisateur de l'organisation ; si le consentement utilisateur est interdit, un administrateur devra accorder le consentement adapté.
5. Déployer d'abord à un seul collaborateur et vérifier nom, e-mail, poste, téléphone, photo et liens.

Les permissions du manifeste Outlook et celles de Microsoft Graph dans Entra sont différentes : `ReadWriteMailbox` permet au complément d'insérer le HTML dans le brouillon ; `User.Read` autorise la lecture du profil Microsoft Graph de l'utilisateur connecté.

Ce dépôt ne permet pas de confirmer à lui seul l'état réel des réglages dans Entra. Ceux-ci doivent être vérifiés dans le tenant CORBE44 avant le test.
