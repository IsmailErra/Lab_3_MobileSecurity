# Lab_3_MobileSecurity -  Observation du trafic HTTP(S) avec Burp Suite

## Objectif

Observer le trafic réseau d’un émulateur Android à l’aide de Burp Suite dans un environnement de laboratoire.

---

## Configuration

* Burp Suite en cours d’exécution
* Proxy listener actif sur `*:8080`
* IP hôte : `192.168.11.101`
* Port proxy : `8080`

---
![Liste](Lab_3_MobileSecurity/4.png)

## Étapes

### 1. Démarrage de Burp

Vérifier que le proxy listener est actif.

![Liste](Lab_3_MobileSecurity/3.png)
![Liste](Lab_3_MobileSecurity/2.png)


---

### 2. Configuration du proxy Android

Dans l’émulateur :

* Wi-Fi → AndroidWifi
* Proxy → Manual
* Host → `192.168.11.101`
* Port → `8080`

![Liste](Lab_3_MobileSecurity/6.png)

---

### 3. Vérification HTTP

Ouvrir le navigateur de l’émulateur et accéder à :

`http://neverssl.com`

Vérifier que des requêtes apparaissent dans **HTTP history**.

![Liste](Lab_3_MobileSecurity/16.png)
![Liste](Lab_3_MobileSecurity/17.png)
![Liste](Lab_3_MobileSecurity/9.png)



---

### 4. Test Intercept

* Activer **Intercept is on**
![Liste](Lab_3_MobileSecurity/11.png)

* Rafraîchir la page
* Observer la requête
![Liste](Lab_3_MobileSecurity/10.png)

* Cliquer **Forward**
* Remettre **Intercept is off**

![Liste](Lab_3_MobileSecurity/1.png)

---

### 5. Principe HTTPS

Observer l’écran **Install a certificate** dans l’émulateur et identifier le rôle du certificat CA pour l’analyse HTTPS en laboratoire.

![Liste](Lab_3_MobileSecurity/22.png)
![Liste](Lab_3_MobileSecurity/13.png)
![Liste](Lab_3_MobileSecurity/12.png)
![Liste](Lab_3_MobileSecurity/14.png)
![Liste](Lab_3_MobileSecurity/15.png)





---

## Nettoyage

* Remettre le proxy Android sur **None**
* ![Liste](Lab_3_MobileSecurity/18.png)

* Supprimer le certificat de laboratoire si installé
![Liste](Lab_3_MobileSecurity/19.png)
![Liste](Lab_3_MobileSecurity/20.png)


* Fermer Burp Suite
![Liste](Lab_3_MobileSecurity/21.png)


---

## Conclusion

Le test confirme que le proxy permet d’observer le trafic de l’émulateur dans un contexte contrôlé.
