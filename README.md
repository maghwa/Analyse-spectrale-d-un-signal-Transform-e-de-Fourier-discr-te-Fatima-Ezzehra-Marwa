# Analyse-spectrale-d-un-signal-Transform-e-de-Fourier-discr-te-Fatima Ennasseri-Marwa Elkamil
## TP1- Analyse spectrale d’un signal /Transformée de Fourier discrète

#### Réalisé par: 
- Fatima  Ennassiri (Filière: Cyber Security)
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

Le concept le plus important dans l'analyse du domaine fréquentiel est la transformation. La transformation est utilisée pour convertir une fonction de domaine temporel en une fonction de domaine fréquentiel et inversement. La transformation la plus courante utilisée dans le domaine fréquentiel est la transformation de Fourier. La transformation de Fourier est utilisée pour convertir un signal de n'importe quelle forme en une somme d'un nombre infini d'ondes sinusoïdales. L'analyse des fonctions sinusoïdales étant plus facile que l'analyse des fonctions de forme générale, cette méthode est très utile et largement utilisée.
Dans ce Tp nous allons exploite la transformée de Fourier discrète qui est un outil mathématique de traitement du signal numérique, qui est l'équivalent discret de la transformée de Fourier continue qui est utilisée pour le traitement du signal analogique.
           
  ### Partie 1: Représentation temporelle et fréquentielle
   - pour calculer  la transformé de fourier a temps discrète sur des signaux suivant le temps on va appliquer la transformée de fourier discrète 

#### 1- Tracer le signal x(t). Fréquence d’échantillonnage : fe = 10000Hz,Nombre d’échantillons : N = 5000



   - pour représenter des signaux num echantionnées dans le domaine fréquentiel de fraquence 10^4 donc on va prends un echantillon dans le signal toute les (1/10^4), et générer un nombre d'échantillon de 5000 échantillons .
   -  d'abord on va confugirer l'axe de temps de t=(0:N-1)*(1/fe), après on génère le signal x. t est de taille 5000. => plot(x,t)
   -  on observe que c'est signal periodique complexe et aussi on observe qu'il est continue et pour afficher le signal réel on va  utiliser des points "plot(x,t,'.')".


  ![amy](https://user-images.githubusercontent.com/120643516/209863872-d2826eae-5b18-46d8-b374-e3644e70f34e.png) ![7](https://user-images.githubusercontent.com/120643516/209864043-78844ec0-8c3c-4f28-8bcd-4e4d8ff400f5.png)
  
  ### =>donc on trouve ici plusieurs points si on calcule on obtient 5000 échantillons.  
  
#### 2- Calculer la TFD du signal x(t) en utilisant la commande fft, puis tracer son spectre 
en amplitude après avoir créé le vecteur f qui correspond à l'échantillonnage du signal 
dans l'espace fréquentiel. Utiliser la commande abs pour afficher le spectre 
d’amplitude.

Pout faire la représentation frequentielle on applique transformé de fourier discrète on utilisant la commande fft(x)
le pas de discritisation dans le domaine fréquentiel >> { fe/N }.


![Q2_partie1](https://user-images.githubusercontent.com/120643516/209865806-490ab1bc-0a9b-415a-999f-4b87cab6f8af.png)

  
  
  ![ploot(fft)](https://user-images.githubusercontent.com/120643516/209865827-92d4c58c-46b9-45f8-8bc1-7bb91d7add14.png)


on va avoir 6 piques , car la transformée de fourier représente la symétrique conjugué c-a-d le spectre est toujours symétrique par rapport a la frequnace d'echantillonage  donc on change l'intervale  on " (N/2:N/2-1)* fe".

 
 #### 3. Pour mieux visualiser le contenu fréquentiel du signal, utiliser la fonction fftshift, qui 
effectue un décalage circulaire centré sur zéro du spectre en amplitude obtenu par la
commande fft.


la transformée de fourier discrète donne les amplitude non normalisé pour les normalisé par rapporrt au nombre d'échantillon donc on dévise les amplitudes sur N et on sait que cette représentation et complexe pour trouver l'amplitude réel on multiple par 2 Cn=An/2.






![Q3_partie1](https://user-images.githubusercontent.com/120643516/209866873-4229c21c-d72f-4dda-a29a-1d29f0280b78.png)


![plot(fftshift)p1 re](https://user-images.githubusercontent.com/120643516/209866884-ce04c7a3-0ed8-4c94-b220-6f865df795ff.png)


#### Un bruit correspond à tout phénomène perturbateur gênant la transmission ou l'interprétation d'un signal. Dans les applications scientifiques, les signaux sont souvent corrompus par du bruit aléatoire, modifiant ainsi leurs composantes fréquentielles. La TFD peut traiter le bruit aléatoire et révéler les fréquences qui y correspond.

#### 4- Créer un nouveau signal xnoise, en introduisant un bruit blanc gaussien dans le 
signal d’origine x(t), puis visualisez-le. Utiliser la commande randn pour générer ce 
bruit. Il est à noter qu’un bruit blanc est une réalisation d'un processus aléatoire dans 
lequel la densité spectrale de puissance est la même pour toutes les fréquences de 
la bande passante. Ce bruit suit une loi normale de moyenne 0 et d’écart type 1.



![Q4_partie1](https://user-images.githubusercontent.com/120643516/209867294-e558e05b-346b-4763-abc4-d452e50fcc95.png)


![plot(bruit)](https://user-images.githubusercontent.com/120643516/209867316-6fe71ff5-c507-46b7-81b0-c5ee07cef5ab.png)


#### 5 – Utiliser la commande sound pour écouter le signal et puis le signal bruité.
pour écouter le bruit on utilise : sound(xnoise), sound(x+xnoise).

#### La puissance du signal en fonction de la fréquence (densité spectrale de puissance)est une métrique couramment utilisée en traitement du signal. Elle est définie comme étant le carré du module de la TFD, divisée par le nombre d'échantillons de fréquence. 


#### 6- Calculez puis tracer le spectre de puissance du signal bruité centré à la fréquence 
zéro. 

![Q6_partie1](https://user-images.githubusercontent.com/120643516/209867794-28ca4071-de8c-4823-b99b-67fcf127231e.png)




![plot(Q6)_partie1](https://user-images.githubusercontent.com/120643516/209867832-0b6ddfa5-1de3-478c-a77b-d9bd870ad524.png)




#### Interprétation de résultat obtenu :

![partie1](https://user-images.githubusercontent.com/120643516/209868536-64b5d92a-a870-4ccb-ab69-87f346e249af.png)



  
  
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

<img width="682" alt="209854805-2ed0faf5-1155-4656-b79c-722b42b396e1" src="https://user-images.githubusercontent.com/87017143/215060898-b167bad4-1f1d-4dfe-9d81-6a2a2d6d1539.png">


On observe une fréquence fondamentale qui est conforme a celle des rorquals bleus qui accordent leurs vocalises de basse fréquence de manière extrêmement précise et uniforme, à une fréquence de 16 H

### Conclusion:
Dans ce Tp ,nous avons pu découvrir la représentation de signaux et les 
applications de la transformée de Fourier discrète (TFD) sous Matlab. Ainsi que ,
l’évaluation de l’intérêt du passage du domaine temporel au domaine fréquentiel 
dans l’analyse et l’interprétation des signaux physiques réels.
