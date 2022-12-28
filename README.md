# Analyse-spectrale-d-un-signal-Transform-e-de-Fourier-discr-te-Fatima-Ezzehra-Marwa
## TP1- Analyse spectrale d’un signal /Transformée de Fourier discrète

#### Réalisé par: 
- Fatima Ezzehra Ennassiri (Filière: Cyber Security)
- Marwa El Kamil(Filière: Artficial Intelligence)
### Encadré par:
- Mr Alae Ammour

### Objectifs:

- Représentation de signaux et applications de la transformée de Fourier discrète 
(TFD) sous Matlab.
- Evaluation de l’intérêt du passage du domaine temporel au domaine fréquentiel 
dans l’analyse et l’interprétation des signaux physiques réels.
### Travail demandé :
Un script Matlab commenté contenant le travail réalisé et des commentaires sur ce 
que vous avez compris et pas compris, ou sur ce qui vous a semblé intéressant ou 
pas, bref tout commentaire pertinent sur le TP.

### Introduction:

Le concept le plus important dans l'analyse du domaine fréquentiel est la 
transformation. La transformation est utilisée pour convertir une fonction de 
domaine temporel en une fonction de domaine fréquentiel et inversement. La 
transformation la plus courante utilisée dans le domaine fréquentiel est la 
transformation de Fourier. La transformation de Fourier est utilisée pour convertir un signal de n'importe quelle forme en une somme d'un nombre infini d'ondes sinusoïdales. L'analyse des fonctions sinusoïdales étant plus facile que l'analyse des fonctions de forme générale, cette méthode est très utile et largement utilisée.
Dans ce Tp nous allons exploite la transformée de Fourier discrète qui est un outil mathématique de traitement du signal numérique, qui est l'équivalent discret de la transformée de Fourier continue qui est utilisée pour le traitement du signal analogique.
           
  ## Partie 1: Représentation temporelle et fréquentielle
  
 (fatii you can write your work here)
 ## Partie 2: Analyse fréquentielle du chant du rorqual bleu
 
 - Introduction :
 
      - Il existe plusieurs signaux dont l’information est encodée dans des sinusoïdes. Les 
ondes sonores est un bon exemple. Considérons maintenant des données audios 
collectées à partir de microphones sous - marins au large de la Californie. On cherche à détecter à travers une analyse de Fourier le contenu fréquentiel d’une onde sonore émise pas un rorqual bleu.

   - Les rorquals bleus accordent leurs vocalises de basse fréquence de manière extrêmement précise et uniforme, à une fréquence de 16 Hz, selon l’étude récemment publiée dans le Journal of the Acoustical Society of America
   - Le but de cet exercice est d’extraire le chant du rorqual bleu du fichier 
‘bluewhale.au’ .Ce chant se trouve entre les deux fréquences x=2.45e4 
z=3.1e4 après on l entend a travers la commande sound et finalement on le trace 
avec la commande plot dans un intervalle de temps 
t=15*(0:1/Fs:(length(rorqualvoice)-1)*(1/Fs))
#### 1-Chargez, depuis le fichier ‘bluewhale.au’, le sous-ensemble de données qui correspond au chant du rorqual bleu du Pacifique.
 On utilise la commande audioread pour lire le fichier. Le son à              récupérer correspond aux indices allant de 2.45e4 à 3.10e4
Voila un aperçu sur le code :
 
 
  <img width="300" alt="Screenshot 2022-12-28 182301" src="https://user-images.githubusercontent.com/87017143/209849554-44788a0c-7198-4837-9e84-8f581fac7e36.png">
  
#### 2- Ecoutez ce signal en utilisant la commande sound, puis visualisez-le.
   - En effet, les appels de rorqual ble sont des sons à basse fréquence, ils sont à peine audibles pour les humains. Pour ces raison on multiplie l'axe temporel en 10
  - On rappelle que la bande de fréquences audibles par l’oreille humaine s’étale de 20 Hz à 20kHz. Lorsque la fréquence est faible, le son est grave (de 20 à 200 Hz). On parle de son médium pour une fréquence comprise entre 200 et 1000 Hz et de son aigu lorsque la fréquence est comprise entre 1000 et 15000 Hz
Voila un aperçu sur le code :
<img width="321" alt="Screenshot 2022-12-28 184206" src="https://user-images.githubusercontent.com/87017143/209851586-5a3c9173-be94-4b40-97b5-e5f1e6fb43e7.png">

<img width="404" alt="Screenshot 2022-12-28 184609" src="https://user-images.githubusercontent.com/87017143/209852144-d46fb351-a7e7-4bd9-9825-2259d03392f2.png">

#### 3- Spécifiez une nouvelle longueur de signal n qui sera une puissance de 2, puis tracer la densité spectrale de puissance du signal.
Pour identifier les composantes fréquentielles de ce signal audio ,on applique la 
transformée de Fourrier

![image](https://user-images.githubusercontent.com/87017143/209854048-a087171a-1861-4358-88df-172a441a325f.png)

Comme vous remarquer dans les lignes de code le signal subit une compression / 10 pour visualiser les fréquences réelles du gémissement de rorqual bleu.

![image](https://user-images.githubusercontent.com/87017143/209854290-4c82b576-7106-4eb9-bed0-d445e10684de.png)

#### 4- Déterminer à partir du tracé, la fréquence fondamentale du gémissement de rorqual bleu.
![209854515-4767cc6d-ff59-4d8e-8d58-04646e82cd4d](https://user-images.githubusercontent.com/87017143/209854767-8b67ba21-a9f4-4bca-bb7f-774fadb9b69e.png)

![image](https://user-images.githubusercontent.com/87017143/209854805-2ed0faf5-1155-4656-b79c-722b42b396e1.png)

On observe une fréquence fondamentale qui est conforme a celle des rorquals bleus qui accordent leurs vocalises de basse fréquence de manière extrêmement précise et uniforme, à une fréquence de 16 H

### Conclusion:
Dans ce Tp ,nous avons pu découvrir la représentation de signaux et les 
applications de la transformée de Fourier discrète (TFD) sous Matlab. Ainsi que ,
l’évaluation de l’intérêt du passage du domaine temporel au domaine fréquentiel 
dans l’analyse et l’interprétation des signaux physiques réels.
