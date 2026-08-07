# ugreen-infra-stack

## Ajouter un domaine

### 1. Créer le domaine dans DuckDNS

Créer le nouveau sous-domaine dans DuckDNS et vérifier qu'il pointe vers la même IP publique que les domaines existants.

### 2. Mettre à jour DuckDNS

Ajouter le sous-domaine à `SUBDOMAINS` dans le `.env` :

```env
SUBDOMAINS=domain1,domain2,domain3
```

### 3. Configurer Nginx Proxy Manager

Créer un nouveau Proxy Host :

* Domain Names : mon-domain.duckdns.org
* Scheme : http
* Forward Hostname / IP : valeur adaptée au service
* Forward Port : port du service
* Block Common Exploits : activé
* Websockets Support : activé

### 4. Configurer le certificat SSL

Dans l'onglet SSL :

* SSL Certificate → Request a new SSL Certificate
* Let's Encrypt
* Force SSL : activé
* HTTP/2 Support : activé
