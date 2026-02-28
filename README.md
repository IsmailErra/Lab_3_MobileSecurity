# Lab_3_MobileSecurity — Observation du trafic HTTP(S) avec Burp Suite

## Objectif

Observation du trafic réseau d’un émulateur Android à l’aide de Burp Suite dans un environnement de laboratoire.

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

Vérification du bon fonctionnement du proxy listener.

![Liste](lab_3_screenshots/3.png)
![Liste](lab_3_screenshots/2.png)

---

### 2. Configuration du proxy Android

Au niveau de l’émulateur :

* Wi-Fi → AndroidWifi
* Proxy configuré en **Manual**
* Host : `192.168.11.101`
* Port : `8080`

![Liste](lab_3_screenshots/6.png)

---

### 3. Vérification HTTP

Accès au site :

`http://neverssl.com`

Constat de l’apparition des requêtes dans **HTTP history**, confirmant le passage du trafic par le proxy.

![Liste](lab_3_screenshots/16.png)
![Liste](lab_3_screenshots/17.png)
![Liste](lab_3_screenshots/9.png)

---

### 4. Test Intercept

Activation temporaire de l’interception afin d’observer la mise en attente d’une requête.
Après observation, transfert de la requête puis désactivation de l’interception.

![Liste](lab_3_screenshots/11.png)
![Liste](lab_3_screenshots/10.png)
![Liste](lab_3_screenshots/1.png)

---

### 5. Principe HTTPS

Observation de l’écran **Install a certificate** dans l’émulateur et identification du rôle du certificat CA dans un contexte d’analyse HTTPS en laboratoire.

![Liste](lab_3_screenshots/22.png)
![Liste](lab_3_screenshots/13.png)
![Liste](lab_3_screenshots/12.png)
![Liste](lab_3_screenshots/14.png)
![Liste](lab_3_screenshots/15.png)

---

## Nettoyage

* Retour du proxy Android sur **None**
  ![Liste](lab_3_screenshots/18.png)

* Suppression du certificat de laboratoire (si présent)
  ![Liste](lab_3_screenshots/19.png)
  ![Liste](lab_3_screenshots/20.png)

* Fermeture de Burp Suite
  ![Liste](lab_3_screenshots/21.png)

---

## Conclusion

Le test met en évidence le rôle du proxy comme point de passage du trafic réseau et confirme le bon fonctionnement de l’observation dans un environnement contrôlé.
