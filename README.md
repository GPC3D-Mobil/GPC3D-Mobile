# GPC3D Mobile V2

Application mobile-first pour le suivi GPC3D. Elle fonctionne comme une PWA et conserve ses données localement sur l’appareil.

## Fonctionnalités

- Tableau de bord mobile
- Clients et historique
- Interventions, avec numérotation automatique GPC3D-AAAA-0001
- Plusieurs passages par intervention
- Produits utilisés en texte libre dans les fiches d’intervention
- Signature client au doigt
- Fiche d’intervention imprimable ou enregistrable en PDF
- Catalogue de produits et gestion manuelle du stock
- Alertes de seuil facultatives et historique des mouvements de stock
- Sauvegarde locale, export et import JSON
- Manifest PWA et service worker pour l’utilisation hors ligne

## Catalogue et stock

La première ouverture ajoute un catalogue de départ. Les stocks initiaux et seuils d’alerte restent à renseigner par l’utilisateur; une valeur inconnue n’est pas interprétée comme un stock nul. Le stock peut ensuite être suivi par des mouvements manuels d’entrée, de sortie et de correction d’inventaire. Les anciennes fiches et leurs produits en texte libre sont conservés.

Les unités de stock disponibles comprennent les blocs, mL, L, g, kg et unité. Les stocks en blocs utilisent des nombres entiers. L’unité d’un produit est verrouillée dès son premier mouvement afin de préserver la cohérence de son historique. Le catalogue n’est pas encore lié aux interventions et les mouvements de stock ne sont donc pas déclenchés automatiquement lors d’une intervention.

Aucun dosage ni calcul d’application n’est activé dans cette phase. Les formulations et étiquettes applicables doivent être vérifiées avant toute fonctionnalité de dosage.

## Données et sauvegardes

Les clients, interventions, signatures, catalogue et mouvements restent dans le stockage local du navigateur/appareil. L’import d’une ancienne sauvegarde contenant des clients et interventions conserve ces données et initialise le catalogue si elle n’en contient pas. Exportez régulièrement le fichier JSON et gardez-en une copie hors de l’appareil. Effacer les données réinitialise aussi le catalogue et l’historique du stock.

La synchronisation cloud sécurisée n’est pas encore disponible. Une sauvegarde locale ne synchronise pas automatiquement les données entre appareils.

## Publication GitHub Pages

Le site est publié depuis la branche `main`, dossier racine (`/`). Une mise à jour envoyée sur cette branche est publiée par GitHub Pages. Le service worker utilise une nouvelle version de cache pour charger les nouveaux fichiers de l’application.

