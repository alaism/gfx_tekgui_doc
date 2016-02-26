<U><font color="#A0522D">**Fonction de la librairie**</font color="#A0522D"></U>
=============
</br></br>

<font color="#A0522D">tekpixel</font color="#A0522D">
---
</br></br>
La fonction tekpixel modifie la couleur d'un pixel a une position donné.</br>
Elle est defénit comme suit:

```
void      tekpixel(t_bunny_pixelarray *pix, t_bunny_position *pos, t_color *color);
```
La fonction tekpixel peut changer la couler uniquement de la taille du pixelarray.</br>
Si la position donné est fausse, la fonction ne changera rien.
---
</br></br>

<font color="#A0522D">tekgui_load</font color="#A0522D">
---
</br></br>
La fonction tekgui_load lit les informations présente dans le fichier ini et remplit la structre getgui.
Il faut appeller cette fonction avant toute autre fonction utilisant la structure tekgui.
tekgui_load est definit comme si-dessous
</br>
```
t_tekgui     tekgui_load(const char *filename);
```
</br>
En cas d'erreur, la fonction tekgui_load retourne NULL et un message s'affichera sur la sorit d'erreur.

------
</br></br><font color="#A0522D">tekgui_display</font color="#A0522D">
------
</br></br>
La fonction tekgui_display ecrit toutes les données contenue dans la structure t_tekgui dans un pixelarray.</br>
**<font color="red">ATTENTION</font color="red"> : tekgui_display ne gère pas l'affichage, elle se contente de "remplir" le pixelarray**</br>
Pour afficher la window, il faut utiliser la fonction [<font color="#AFEEEE">display_window</font color="#AFEEEE">](./fonction-fr/#display_window) </br>
tekgui_display est définit comme si-dessous

```
void       tekgui_display(t_bunny_pixelarray *pix, t_tekgui *tekgui);
```
</br></br>
Pour plus de simplicité, il est recommandé d'utiliser la fonction comme suit:

```
tekgui_display(tekgui->pix, tekgui);
```

-------
</br></br><font color="#A0522D">display_window</font color="#A0522D">
-------
</br></br>
La fonction display_window affiche la fenêtre avec toutes la structure.

```
void      display_window(t_tekgui *tekgui);
```
</br></br>
Cette fonction affiche l'image, mais ne la remplit pas le pixelarray.</br>
Pour remplir l'amage, il faut utiliser [<font color="#AFEEEE">tekgui_display</font color="#AFEEEE">](./fonction-fr/#tekgui_display)</br>

---
</br></br><font color="#A0522D">tekfunction</font color="#A0522D">
---
</br></br>
La fonction tekfunction prend en parametre le nom d'une fonction et renvoi l'adresse de cette fonction.</br>
Elle est definit comme suit:

```
void      *tekfunction(const char *functname);
```
</br></br>
Si la fonction n'existe pas ou qu'une erreur c'est produite, tekfunction va renvoyer NULL.</br>

---
</br></br><font color="#A0522D">tektext</font color="#A0522D">
---
</br></br>
Cette fonction afficher du text en Haut a gauche du pixelarray.</br>
Elle prend en parametre le pixelarray de destinaltion, une chaine de carractère a copier, et un pixelarray contenant les caractères</br>
Elle est definit comme suit:

```
void tektext(t_bunny_pixelarray *out, const char *str, t_bunny_pixelarray *font_png);
```

---
</br></br><font color="#A0522D">tekgetpixel</font color="#A0522D">
---
</br></br>
La fonction tekgetpixel prend en parametre la position d'un pixel et renvoi sa couleur.</br>
Elle est definit comme suit :</br>
```
t_color      tekgetpixel(t_bunny_pixelarray *, t_bunny_position *);
```

---
</br></br><font color="#A0522D">tekgui_stop</font color="#A0522D">
---
</br></br>
La fonction tekgui_stop libère la memmoire accuper par la librairie.</br>
Elle doit abligatoirement etre appelé.</br>
```
void      tekgui_stop(t_tekgui *);
```

---
</br></br><font color="#A0522D">tekgui_max_ram</font color="#A0522D">
---
</br></br>
La fonction tekgui_max_ram prend en parametre le fichier ini qui correspond au projet.</br>
Elle est definit comme suit :</br>
```
void    tekgui_max_ram(const char *name);
```

Elle définit le maximum de ram qui peut etre utiliser par le programme.</br>
Il faut l'appeler au debut du programme, avant [<U><font color="#AFEEEE">tekgui_load</font color="#AFEEEE"></U>](./fonction-fr/#tekgui_load)
