# Philosophers

**Philosophers** est une implémentation classique du problème des **dîneurs philosophes**  
qui met en pratique la **programmation concurrente**, la création de threads et l’utilisation
de **mutex** pour éviter les accès concurrents à des ressources partagées.

L’objectif est d’éviter les conditions de famine et les blocages (deadlocks).

---

## 🧠 Problématique

Des philosophes sont assis autour d’une table circulaire.  
Chaque philosophe alterne 3 états :

🧠 penser → 🍝 manger → 😴 dormir

Pour manger, il doit prendre **deux fourchettes** :
- celle à sa gauche
- celle à sa droite

Mais comme les fourchettes sont partagées → risques :
- deadlock : tout le monde attend une fourchette…
- starvation : un philosophe ne mange jamais → il meurt

🎯 Mission : faire en sorte que **personne ne meure** (du moins tant que la règle le permet !)

---

## Compilation

```sh
make
./philo number_of_philosophers time_to_die time_to_eat time_to_sleep \
[number_of_times_each_philosopher_must_eat]
./philo 5 800 200 200
timestamp philosopher_id <action>

Exemple visuel console:
120 1 has taken a fork
120 1 has taken a fork
121 1 is eating
300 1 is sleeping
500 1 is thinking
```

## Nettoyage

```sh
make clean
make fclean
make re
```

📌 Règles critiques
🚫 Chaque philosophe = un thread
🚫 Chaque fourchette = un mutex
🚫 Aucun accès concurrent sans protection
🚫 Pas de data races
🚫 Aucune variable globale

timestamp philosopher_id <action>

```sh
Actions :
has taken a fork 🍴
is eating 🍝
is sleeping 😴
is thinking 🤔
died 💀 (doit être affiché dans les 10ms)
```
