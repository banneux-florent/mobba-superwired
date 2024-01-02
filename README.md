# SuperWired (Effet)
## Informations

Le mobis "Effet WIRED: SuperWired" est toujours en cours de développement. Il a été recoder entièrement et demande des tests afin de valider ses capacités. **Si vous rencontrez des bugs, merci de bien vouloir les signaler!** Ils sont éventuellement à prévoir et seront résolus dans les plus brefs délais.

**Les exemples et instructions se trouvent en bas de page.**

# Commandes

*cf. "Paramètres existants" pour définition de `base`*

## Avec valeur
➕**enable**:<id (0-199, 500-688, 700)> [base]  
➕**enableall**:<id (0-199, 500-688, 700)> [base]  
➕**handitem**:<id (0-138)> [base]  
➕**handitemall**:<id (0-138)> [base]  
➕**dance**:<id (0-4)> [base/ad-f:value]  
➕**danceall**:<id (0-4)> [base/ad-f:value]  
➕**rotate**:<direction (0-7)> [base/ad-irh]  
➕**rotateall**:<direction (0-7)> [base/ad-irh]  
➕**setspeed**:<speed (0-100)> [base/ad-f:value]  
➕**moonwalk**:<true|false|toggle> [base/ad-f:value]  
➕**moonwalkall**:<true|false|toggle> [base/ad-f:value]  
➕**fastwalk**:<true|false|toggle> [base/ad-f:value]  
➕**fastwalkall**:<true|false|toggle> [base/ad-f:value]  
➕**roomdiagonal**:<true|false|toggle> [duration/delay/ad-f:value]  
➕**roomlock**:<true|false|toggle> [duration/delay/ad-f:value]  
➕**roomingame**:<true|false|toggle> [duration/delay/ad-f:value]  

#### Rank requit:

➕**givediamonds**:\<int> [delay] **(Rank 7+)**  
➕**giveduckets**:\<int> [delay] **(Rank 7+)**  
➕**givediamonds**:\<int> [delay] **(Rank 7+)**  

## Sans valeur
➕**enable** (random) [base]  
➕**enableall** (random) [base]  
➕**disable** [base]  
➕**disableall** [base]  
➕**handitem** (random) [base]  
➕**handitemall** (random) [base]  
➕**dance** (random) [base/ad-f:value]  
➕**danceall** (random) [base/ad-f:value]  
➕**rotate** (random) [base/ad-irh]  
➕**rotateall** (random) [base/ad-irh]  
➕**sit** [base/ad-f]  
➕**sitall** [base/ad-f]  
➕**stand** [base]  
➕**standall** [base]  
➕**lay** [base]  
➕**layall** [base]  
➕**freeze** [base]  
➕**freezeall** [base]  
➕**unfreeze** [base]  
➕**unfreezeall** [base]  
➕**resetspeed** (identique à "setspeed:4") [base]  
➕**moonwalk** (mode toggle) [base/ad-f]  
➕**moonwalkall** (mode toggle) [base/ad-f]  
➕**fastwalk** (mode toggle) [base/ad-f]  
➕**fastwalkall** (mode toggle) [base/ad-f]  
➕**roomdiagonal** (mode toggle) [duration/delay/ad-f]  
➕**roomlock** (mode toggle) [duration/delay/ad-f]  
➕**roomingame** (mode toggle) [duration/delay/ad-f]  

# Paramètres supplémentaires

**`delay` est disponnible sur TOUTES les commandes.**

`base` = [duration/surface/except-surface/players-only/staffs-only]

## Avec valeur
➕**surface:(x1;y1)(x2;y2)** - *n'active l'effet que sur cette surface*  
➕**except-surface:(x1;y1)(x2;y2)** - *Active l'effet partout sauf sur cette surface*  
➕**delay**:<int = infini> - *Exécute la commande après une certaine durée*  
➕**delay_unit**:<h|m|s|ms = s> - *[`delay` requit] Défini l'unité de temps du paramètre `delay`*  
➕**duration**:<int = infini> - *Active pendant une certaine durée*  
➕**duration_unit**:<h|m|s|ms = s> - *[`duration` requit] Défini l'unité de temps du paramètre `delay`*  
➕**ad-f**:<reset|previous> - *[`duration` requit] after-duration-force: force l'effet à revenir à sa valeur initiale ou à sa valeur antérieure à l'exécution de la commande*  

## Sans valeur
➕**players-only**/**except-staffs** - *n'active l'effet que pour les joueurs et non les staffs*  
➕**staffs-only**/**except-players** - *n'active l'effet que pour les staffs et non les joueurs*  
➕**ad-f** - *[`duration` requit] after-duration-force: force l'effet à revenir à sa valeur initiale après exécution de la commande*  
➕**ad-irh** - *[`duration` requit] after-duration-ignore-rotated-habbos: ignore les habbos ayant changé de rotation durant la période de `duration`*  

# Exemples et instructions

Les commandes entières peuvent être enchaînées lorsqu'elles sont séparées par des barres verticales (`|`):  
```rotateall:1 direction:clockwise|enableall:1 duration:1500 duration_unit:ms```  
<sub>*Tourne tous les joueurs de 1 cran dans le sens horloger tout en leur activant l'effet 1 pendant 1500ms (1.5s).*</sub>

Les paramètres peuvent être enchaînées lorsqu'ils sont séparés par des espaces (` `):  
```enable:1 only-players surface:(3;7)(13;11) duration:10 delay:3 ad-f:previous```  
<sub>*Active l'effet 1 pour les joueurs de rank inférieur à 4, se trouvant dans la surface donnée, pour une durée de 10 secondes, 3 secondes après le déclenchement du wired, avec un retour à l'effet précédent à la fin de la durée.*</sub>
