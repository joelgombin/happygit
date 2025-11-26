# Configuration Matomo et Bluesky

Ce guide explique comment finaliser la configuration de Matomo Analytics et des métadonnées Bluesky pour votre site.

## 📊 Configuration Matomo Analytics

Matomo est une alternative open-source et respectueuse de la vie privée à Google Analytics.

### ✅ Configuration actuelle

Le tracking Matomo est **déjà configuré** dans `matomo-analytics.html` :
- **URL Matomo** : `matomo.apps.joelgombin.fr`
- **Site ID** : `2`

### Vérifier le fonctionnement

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

### ✅ Configuration actuelle

Le handle Bluesky est **déjà configuré** dans `_quarto.yml` :
```yaml
twitter-card:
  creator: "@joelgombin.fr"
  site: "@joelgombin.fr"
```

**Note** : Le handle personnalisé `@joelgombin.fr` est utilisé (domaine personnalisé Bluesky).

### Profils sociaux configurés

Les profils suivants sont intégrés dans les métadonnées SEO et Schema.org :
- **GitHub** : https://github.com/joelgombin
- **LinkedIn** : https://www.linkedin.com/in/jgombin/
- **Bluesky** : https://bsky.app/profile/joelgombin.fr

Ces liens apparaissent dans :
- La navbar du site (GitHub et LinkedIn)
- Les données structurées Schema.org
- Les métadonnées pour les moteurs de recherche

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

### Configuration complétée ✅
- [x] Configurer Matomo Analytics dans `matomo-analytics.html` (matomo.apps.joelgombin.fr, Site ID: 2)
- [x] Vérifier les handles Bluesky dans `_quarto.yml` (@joelgombin.fr)
- [x] Ajouter les profils sociaux (GitHub, LinkedIn, Bluesky)
- [x] Créer le fichier CNAME pour le domaine personnalisé

### À faire pour le déploiement
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
