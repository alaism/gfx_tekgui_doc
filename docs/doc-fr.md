<U><font color="#A0522D">**Utilisation de la librairie tekgui**</font color="#A0522D"></U>
===============
</br></br>
Ce guide est fait pour les utilisateurs qui connaissent les bases de la Liblapin, et qui maîtrisent les fonctions :

```c
bunny_set_key_response();
bunny_set_loop_main_function();
bunny_loop();
```

------
</br></br><U><font color="#A0522D">Création d'un fichier ini</font color="#A0522D"></U>
------
</br></br>
La librairie tekgui se base sur un fichier ini pour créer une interface graphique personalisée.</br>
Il est donc nécessaire de créer un fichier ini correctement.</br>
Certaine partie sont obligatoires, d'autre sont personalisables.
Le fichier ini doit être configuré comme dans l'exemple ci-dessous.</br>
Dans le cas contraire, les fonctions de la librairie tekgui vont renvoyer une erreur.</br>
</br></br>
Exemple :

```
[info]
name="window"
height=800
width=800
color=200,200,200
max_ram=15
```
</br>
Le champ `[info]` est __obligatoire__.</br>
Le champ `window` contient le nom de la fenêtre créée par la librairie.</br>
Les champs `height` et `width` contiennent la longueur et la largeur de la fenetre.</br>
Le champ `color` contient la couleur de la fenetre.</br>
Le champ `max_ram` contient le maximum de ram utilisable par la programme.</br>
Si l'erreur <font color="RED">*Error: error in malloc*</font color="RED"> apparait, c'est probablement que max_ram est trop petit pour supporter la librairie Tekgui.</br>
Si window, color, height ou width n'est pas complété ou existant, les fonctions retourneront une erreur.</br>

------
</br></br><U><font color="#A0522D">Initialisation du fichier ini</font color="#A0522D"></U>
------
</br></br>
La suite du fichier ini contient les informations principales de la fenêtre.
</br></br>
Exemple :

```
[window]
nbr_button=3
name_button=button1,button2,button3
nbr_textbox=2
name_textbox=textbox1,textbox2
nbr_checkbox=2
name_checkbox=checkbox1,checkbox2
nbr_picbox=2
name_picbox=picbox1,picbox2
```
</br>
Le champ `[window]` est obligatoire.</br>
Le champ `nbr_button` est le nombre de bouton présent dans la fenètre.</br>
Le champ `name_button` contient les nom des boutons. Le nombre de nom et `nbr_button` doivent etre les même.</br>
Le champ `nbr_textbox` est le nombre de case de text présent dans la fenêtre.</br>
Le champ `name_textbox` contient les noms des cases de text. Le nombre de nom et `nbr_textbox doivent` etre les même.</br>
Le champ `nbr_checkbox` est le nombre de checkbox présent dans la fenêtre.</br>
Le champ `name_checkbox` contient les noms des cases de text. Le nombre de nom et `nbr_checkbox` doivent etre les même.</br>
Le champ `nbr_picbox` est le nombre d'image présent dans la fenêtre.</br>
Le champ `name_picbox` contient les noms des images. Le nombre de nom et `nbr_picbox` doivent etre les même.</br>
__ATTENTION__ Tous les champ doivent apparaitre dans le fichier ini.</br>
Si, par exemple, vous ne voulez pas de checkbox, voici comment faire :
```
[window]
nbr_button=3
name_button=button1,button2,button3
nbr_textbox=2
name_textbox=textbox1,textbox2
nbr_checkbox=0
name_checkbox=NULL
nbr_picbox=2
name_picbox=picbox1,picbox2

```
-----
</br></br><U><font color="#A0522D">Configuration des boutons</font color="#A0522D"></U>
-----
</br></br>
Apres avoir été initialisé, chaque bouton doit être defini comme dans l'exemple ci-dessous.
</br></br>
Exemple :

```ini
[button1]
name="salut"
posx=0
posy=0
height=100
width=100
color=70,70,70
select_color=150,150,150
fct_to_call="button1"
```
</br>
Le champ `[button1]` contient le nom du bouton que vous voulez definir, entourée de [ ].</br>
Le champ `name` contient le nom du bouton dans la fenêtre.</br>
Les champ `posx` et `posy` contiennent la position de départ du bouton.</br>
Les champ `height` et `wight` définissent la taille du bouton.</br>
Le champ `color` est la couleur du boutton.</br>
Le champ `select_color` est la couleur lorsque le bouton est selectionné.</br>
Le champ `fct_to_call` contient le nom de la fonction appeller lorsque le bouton est cliquer.</br>
Chaque bouton doit avoir sa propre configuration.</br>
Si il y a deux configurations différentes pour le même bouton, la première configuration trouvé sera activée, la seconde sera ignorée.


-----
</br></br><U><font color="#A0522D">Configuration des boîtes de texte</font color="#A0522D"></U>
-----
</br></br>
Apres avoir été initialisé, chaque boîte de texte doit être définie comme dans l'exemple ci-dessous.
</br></br>
Exemple :

```ini
[textbox1]
name="tekbox1"
posx=300
posy=100
height=100
width=300
color=80,80,80
text="bonjour"
```
</br>
Le champ `[textbox1]` contient le nom de la boite que vous voulez definir, entourée de [ ].</br>
Le champ `name` contient le nom de la textbox dans la fenêtre.</br>
Les champ `posx` et `posy` contiennent la position de départ de la textbox.</br>
Les champ `height` et `wight` définissent la taille de la boite.</br>
Le champ `color` contient la couleur de la textbox.</br>
Le champ `text` contient l'écriture initial à l'intérieur de la boite.</br>
</br>
Chaque boite de texte doit avoir sa propre définition.</br>
Si il y a deux configurations différentes pour la même boite, la première configuration trouvé sera activée, la seconde sera ignorée.</br>
Pour utiliser la boite de texte, il suffit de cliquer dessus.</br>
Seul les caractères alphabétiques, les espaces et la touche retour arrière peuvent être utilisé dans ses boîtes</br>
Les autres carractères n'auront uncun effet.</br>
</br>

-----
</br></br><U><font color="#A0522D">Configuration des Checkbox</font color="#A0522D"></U>
-----
</br></br>
Apres avoir été initialisé, chaque checkbox doit être définie comme dans l'exemple ci-dessous.
</br></br>
Exemple :

```ini
[checkbox1]
name="checkbox1"
posx=700
posy=70
height=50
width=50
fct_to_call_check="check"
fct_to_call_not_check="not_check"

```
</br>
Le champ `[textbox1]` contient le nom de la checkbox que vous voulez définir, entourée de [ ].</br>
Le champ `name` contient le nom de la checkbox dans la fenêtre.</br>
Les champ `posx` et `posy` contiennent la position de départ de la checkbox.</br>
Les champ `height` et `wight` définissent la taille de la checkbox.</br>
Le champ `fct_to_call_check` contient le nom de la fonction à appller lorsque la case est cochée</br>
le chemp `fct_to_call_not_check` contient le nom de la fonction à appeller lorque la case n'est pas cochée</br>
</br>
Chaque checkbox doit avoir sa propre définition.</br>
Si il y a deux configurations différentes pour la même checkbox, la première configuration trouvé sera activée, la seconde sera ignorée.</br>
Il suffit de cliquer sur la checkbox pour changer sont etat.</br>
</br>

-----
</br></br><U><font color="#A0522D">Configuration des picbox</font color="#A0522D"></U>
-----
</br></br>
Apres avoir été initialisé, chaque picbox doit être defini comme dans l'exemple ci-dessous.</br>
Le picbox veut dire Picture box, ou "boite d'image"
</br></br>
Exemple :

```ini
[picbox1]
name="emoji6.png"
posx=100
posy=250
```
</br>
Le champ `[picbox1]` contient le nom de la picbox que vous voulez definir, entourer de [ ].</br>
Le champ `name` contient le lien de l'image a charger.</br>
Les champ `posx` et `posy` contiennent la position de départ de la checkbox.</br>
</br>
Chaque picbox doit avoir sa propre definition.</br>
Si il y a deux configurations différentes pour la meme picbox, la première configuration trouvé sera activée, la seconde sera ignorée.</br>
L'image sera affiché à partir des coordonnées donné, jusqu'a sa fin.</br>
Si la fin de l'image se trouve après la fin de la fenètre, une erreur apparaitra dans la terminal.</br>
`name` doit contenir un lien direct ou le chemin d'accés à votre image à partir de la racine de la librairie.</br>
Si l'image donnée n'existe pas ou que le lien est mal entée, la fonction retournera une erreur.</br>
</br>

-----
</br></br><U><font color="#A0522D">Aide</font color="#A0522D"></U>
-----
Pour tester ses fonctions, vous pouver vous servir du fichier ini donner [<U><font color="#AFEEEE">ici</font color="#AFEEEE"></U>](./exemple-ini.md)</br>
Pour tester la librairie avec le fichier ini, il vous faudra un programme.</br>
Un code basique vous est donné [<U><font color="#AFEEEE">ici</font color="#AFEEEE"></U>](./basic-c-program.md)</br></br></br>
---
<U><font color="#A0522D">Les fonctions de la librairie</font color="#A0522D"></U>
---

Toutes les fonctions présente dans la librairie  sont dans l'onglet  [<font color="#AFEEEE">fonction</font color="#AFEEEE">](./fonction-fr)

Si vous chercher une fonction spécifique, vous pourver cliquer qur les lien suivant:  
</br>
</br>
1. [<U><font color="#AFEEEE">tekgui_load</font color="#AFEEEE"></U>](./fonction-fr/#tekgui_load)</br>
2. [<U><font color="#AFEEEE">tekgui_display</font color="#AFEEEE"></U>](./fonction-fr/#tekgui_display)</br>
3. [<U><font color="#AFEEEE">display_window</font color="#AFEEEE"></U>](./fonction-fr/#display_window)</br>
4. [<U><font color="#AFEEEE">tekpixel</font color="#AFEEEE"></U>](./fonction-fr/#tekpixel)</br>
5. [<U><font color="#AFEEEE">tekfunction</font color="#AFEEEE"></u>](./fonction-fr/#tekfunction)</br>
6. [<U><font color="#AFEEEE">tektext</font color="#AFEEEE"></U>](./fonction-fr/#tektext)</br>
7. [<U><font color="#AFEEEE">tekgetpixel</font color="#AFEEEE"></U>](./fonction-fr/#tekgetpixel)</br>
8. [<U><font color="#AFEEEE">tekgui_stop</font color="#AFEEEE"></U>](./fonction-fr/#tekgui_stop)</br>
9. [<U><font color="#AFEEEE">tekgui_max_ram</font color="#AFEEEE"></U>](./fonction-fr/#tekgui_max_ram)</br>
