# Configuration Matomo et Bluesky

Ce guide explique comment finaliser la configuration de Matomo Analytics et des métadonnées Bluesky pour votre site.

## 📊 Configuration Matomo Analytics

Matomo est une alternative open-source et respectueuse de la vie privée à Google Analytics.

### Étape 1 : Obtenir vos informations Matomo

Si vous avez déjà une instance Matomo :
1. Connectez-vous à votre tableau de bord Matomo
2. Notez votre **URL Matomo** (ex: `analytics.example.com` ou `matomo.yoursite.com`)
3. Notez votre **Site ID** (visible dans Administration > Sites web, généralement 1, 2, 3...)

Si vous n'avez pas encore Matomo :
- **Option 1 - Matomo Cloud** : Inscrivez-vous sur https://matomo.org/cloud/
- **Option 2 - Auto-hébergé** : Installez Matomo sur votre serveur (https://matomo.org/download/)

### Étape 2 : Configurer le tracking

1. Ouvrez le fichier `matomo-analytics.html`
2. Remplacez `MATOMO_URL` par votre URL Matomo (sans https://)
   - Exemple : `analytics.example.com` ou `matomo.yoursite.com`
3. Remplacez `SITE_ID` par votre Site ID
   - Exemple : `1` ou `2` ou `3`

**Exemple de configuration :**
```javascript
var u="//analytics.example.com/";  // ← Votre URL Matomo
_paq.push(['setTrackerUrl', u+'matomo.php']);
_paq.push(['setSiteId', '1']);  // ← Votre Site ID
```

### Étape 3 : Vérifier le fonctionnement

Après avoir déployé le site :
1. Visitez votre site web
2. Connectez-vous à votre tableau de bord Matomo
3. Vérifiez que votre visite apparaît dans les visiteurs en temps réel

### Avantages de Matomo

✅ **Respectueux de la vie privée** : Conforme RGPD par défaut
✅ **Propriété des données** : Vos données vous appartiennent
✅ **Pas de limitation** : Tracking illimité sans surcoût
✅ **Open source** : Code source disponible et auditable
✅ **Pas de cookie consent requis** : Si configuré correctement

## 🦋 Configuration Bluesky

Bluesky est le réseau social décentralisé où partagent les créateurs et développeurs.

### Twitter Cards avec Bluesky

Les Twitter Card metadata fonctionnent aussi sur Bluesky ! Quand quelqu'un partage votre lien sur Bluesky, les métadonnées Open Graph et Twitter Card s'affichent automatiquement.

### Handles actuels configurés

Dans `_quarto.yml`, j'ai configuré :
```yaml
twitter-card:
  creator: "@joelgombin.bsky.social"
  site: "@happygit4vibecoders.bsky.social"
```

### Comment les mettre à jour ?

1. **Vérifiez votre handle Bluesky** :
   - Connectez-vous à Bluesky
   - Votre handle est visible dans votre profil (ex: `@username.bsky.social`)

2. **Mettez à jour `_quarto.yml`** si nécessaire :
   - `creator` : Votre handle personnel
   - `site` : Le handle du site/projet (si vous en avez créé un)

3. **Handles personnalisés** :
   - Vous pouvez utiliser un domaine personnalisé comme handle
   - Ex: `@joelgombin.com` au lieu de `@joelgombin.bsky.social`
   - Suivez les instructions Bluesky pour configurer un handle personnalisé

### Test des métadonnées sociales

Pour vérifier que vos métadonnées fonctionnent :

1. **Bluesky** : Partagez votre lien, vérifiez que la carte s'affiche
2. **LinkedIn** : Les métadonnées Open Graph devraient fonctionner
3. **Slack/Discord** : Partagez le lien, vérifiez l'aperçu

## 🌐 Configuration du domaine personnalisé

### Pour GitHub Pages

1. **Créer un fichier CNAME** (déjà fait !) :
   - Le fichier `CNAME` contient : `happygit4vibecoders.com`
   - Il sera copié dans le dossier `docs/` lors du build Quarto

2. **Configurer votre DNS** :
   - Ajoutez un enregistrement A pointant vers les serveurs GitHub :
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - OU ajoutez un CNAME pointant vers `<username>.github.io`

3. **Activer le domaine personnalisé dans GitHub** :
   - Allez dans Settings > Pages
   - Entrez `happygit4vibecoders.com` dans "Custom domain"
   - Activez "Enforce HTTPS"

### Vérification SSL/TLS

Une fois le domaine configuré :
- GitHub Pages génère automatiquement un certificat SSL
- Attendez quelques minutes pour la propagation DNS
- Vérifiez que `https://happygit4vibecoders.com` fonctionne

## 📝 Checklist de déploiement

- [ ] Configurer Matomo Analytics dans `matomo-analytics.html`
- [ ] Vérifier les handles Bluesky dans `_quarto.yml`
- [ ] Configurer le DNS pour pointer vers GitHub Pages
- [ ] Activer le domaine personnalisé dans GitHub Settings
- [ ] Vérifier que le certificat SSL est actif
- [ ] Tester le site sur `https://happygit4vibecoders.com`
- [ ] Vérifier que Matomo enregistre les visites
- [ ] Tester le partage sur Bluesky/LinkedIn/Slack
- [ ] Soumettre le sitemap à Google Search Console
- [ ] Soumettre le sitemap à Bing Webmaster Tools

## 🔍 Ressources utiles

- [Matomo Cloud](https://matomo.org/cloud/)
- [Documentation Matomo](https://matomo.org/docs/)
- [Bluesky](https://bsky.app/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Configurer un domaine personnalisé](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

## 🆘 Support

Si vous rencontrez des problèmes :
- **Matomo** : https://forum.matomo.org/
- **Bluesky** : https://blueskyweb.xyz/support
- **GitHub Pages** : https://github.com/orgs/community/discussions

Bon déploiement ! 🚀
