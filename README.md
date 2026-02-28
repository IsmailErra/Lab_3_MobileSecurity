# Lab_3_MobileSecurity — Observation du trafic HTTP(S) avec Burp Suite

## Objectif

Observer le trafic réseau d’un émulateur Android à l’aide de Burp Suite dans un environnement de laboratoire.

---

## Configuration

* Burp Suite en cours d’exécution
* Proxy listener actif sur `*:8080`
* IP hôte : `192.168.11.101`
* Port proxy : `8080`

![Liste](lab_3_screenshots/4.png)

---

## Étapes

### 1. Démarrage de Burp

Vérifier que le proxy listener est actif.

![Liste](lab_3_screenshots/3.png)
![Liste](lab_3_screenshots/2.png)

---

### 2. Configuration du proxy Android

Dans l’émulateur :

* Wi-Fi → AndroidWifi
* Proxy → Manual
* Host → `192.168.11.101`
* Port → `8080`

![Liste](lab_3_screenshots/6.png)

---

### 3. Vérification HTTP

Dans le navigateur de l’émulateur, ouvrir :

`http://neverssl.com`

Vérifier que des requêtes apparaissent dans **HTTP history**.

![Liste](lab_3_screenshots/16.png)
![Liste](lab_3_screenshots/17.png)
![Liste](lab_3_screenshots/9.png)

---

### 4. Test Intercept

* Activer **Intercept is on**
  ![Liste](lab_3_screenshots/11.png)

* Rafraîchir la page

* Observer la requête
  ![Liste](lab_3_screenshots/10.png)

* Cliquer **Forward**

* Remettre **Intercept is off**

![Liste](lab_3_screenshots/1.png)

---

### 5. Principe HTTPS

Observer l’écran **Install a certificate** dans l’émulateur et identifier le rôle du certificat CA pour l’analyse HTTPS en laboratoire.

![Liste](lab_3_screenshots/22.png)
![Liste](lab_3_screenshots/13.png)
![Liste](lab_3_screenshots/12.png)
![Liste](lab_3_screenshots/14.png)
![Liste](lab_3_screenshots/15.png)

---

## Nettoyage

* Remettre le proxy Android sur **None**
  ![Liste](lab_3_screenshots/18.png)

* Supprimer le certificat de laboratoire si installé
  ![Liste](lab_3_screenshots/19.png)
  ![Liste](lab_3_screenshots/20.png)

* Fermer Burp Suite
  ![Liste](lab_3_screenshots/21.png)

---

## Conclusion

Le test confirme que le proxy permet d’observer le trafic de l’émulateur dans un contexte contrôlé.
