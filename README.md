````md id="lab11gpsmap"
# LAB 11 — GPS et Google Maps Activity

![Android](https://img.shields.io/badge/Platform-Android-green)
![GoogleMaps](https://img.shields.io/badge/API-Google%20Maps-blue)
![Java](https://img.shields.io/badge/Language-Java-orange)

## 📌 Description

Ce laboratoire montre comment intégrer Google Maps dans une application Android et récupérer la position GPS du smartphone.

Objectifs :

- afficher Google Maps ;
- demander les permissions GPS ;
- écouter les changements de position ;
- afficher un marker dynamique ;
- zoomer automatiquement sur la position.

---

# ⚙️ Prérequis

- Android Studio
- Google Maps API Key
- Android SDK
- Connexion internet

---

# 🚀 Partie 1 — Création du Projet

Créer :

```text id="m8v2qa"
Google Maps Activity
````
<img width="1331" height="856" alt="image" src="https://github.com/user-attachments/assets/a323d541-2100-4746-8cc8-8b88cf37b06e" />

Android Studio génère automatiquement :

* MapsActivity.java
* activity_maps.xml
* google_maps_api.xml

---

# 🔑 Partie 2 — Clé API Google Maps

Dans :

```text id="q3w7ld"
google_maps_api.xml
```

Ajouter :

```xml id="t9x4pr"
<string name="google_maps_key">
YOUR_API_KEY
</string>
```
<img width="399" height="312" alt="image" src="https://github.com/user-attachments/assets/05cb641e-ea2f-4e4e-8784-045ce063b36a" />

---

# 📱 Partie 3 — Permissions Android

Dans `AndroidManifest.xml`

```xml id="g6p1mk"
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.INTERNET"/>
```
<img width="113" height="250" alt="image" src="https://github.com/user-attachments/assets/75ab3bb8-aee3-401d-bfb0-a2b856236446" />

---
<img width="76" height="163" alt="image" src="https://github.com/user-attachments/assets/7d458a73-f523-43f3-b2f1-42b14b7afc62" />

# 🗺 Partie 4 — onMapReady()

Exemple :

```java id="k2r8yn"
@Override
public void onMapReady(GoogleMap googleMap) {

    mMap = googleMap;

    LatLng position = new LatLng(31.6295, -7.9811);

    mMap.addMarker(new MarkerOptions().position(position));

    mMap.moveCamera(CameraUpdateFactory.newLatLngZoom(position,15));
}
```

---

# 📍 Partie 5 — Permissions Runtime

Demander permission :

```java id="p5m7xs"
ActivityCompat.requestPermissions(
this,
new String[]{Manifest.permission.ACCESS_FINE_LOCATION},
1
);
```

---

# 🔥 Partie 6 — Marker Dynamique

Mettre à jour le marker :

```java id="w8t3qa"
mMap.clear();

mMap.addMarker(
new MarkerOptions().position(currentPosition)
);
```

---

# ⚡ Partie 7 — GPS Désactivé

Afficher une boîte de dialogue :

```java id="x4v1ru"
startActivity(
new Intent(Settings.ACTION_LOCATION_SOURCE_SETTINGS)
);
```

---

# ✅ Résultat Attendu

* carte Google Maps affichée
* GPS fonctionnel
* marker mis à jour
* zoom automatique

---

# 🛠 Problèmes Fréquents

| Problème           | Solution                    |
| ------------------ | --------------------------- |
| Carte blanche      | vérifier API Key            |
| GPS non détecté    | activer localisation        |
| Permission refusée | accepter runtime permission |

---

# 📚 Concepts Appris

* Google Maps API
* GPS Android
* Runtime Permissions
* Markers
* Camera Zoom

---

# 👨‍💻 Auteur

Ayoub Laafar — EMSI Marrakech

```
```
