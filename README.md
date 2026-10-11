# CORBÉ 44 — Signature mobile

Préparation du complément Outlook mobile à tester uniquement sur le compte de test CORBÉ 44.

## Fichiers
- `manifest.xml` : manifeste du complément CORBÉ 44, avec un identifiant distinct de CORBÉ 49.
- `mobile.js` : code de composition de la signature et accès au profil via Microsoft Graph.
- `mobile.html` et `auth.html` : pages hébergées sur GitHub Pages.

## Configuration Entra CORBÉ 44 déjà appliquée
- Application : `CORBE44-Signature-Mobile`
- Client ID : `4e53fe58-6711-4d92-b141-c90f8ca3b550`
- Tenant ID : `63fb9113-5dd8-452e-9c0b-279a1e9170cc`
- URI de redirection SPA : `https://xaviouk.github.io/corbe44-signature-mobile/auth.html`
- Permission déléguée attendue : Microsoft Graph `User.Read`

## Important
Ce paquet n'a pas encore été validé dans Outlook réel. Déployer d'abord uniquement sur le compte de test CORBÉ 44. Ne pas modifier le complément CORBÉ 49. Vérifier ensuite que l'événement de composition s'exécute et que l'authentification Graph fonctionne.
