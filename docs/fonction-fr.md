<U><font color="#A0522D">**Fonction de la librairie**</font color="#A0522D"></U>
=============
</br></br>

<font color="#A0522D">tekpixel</font color="#A0522D">
---
</br></br>
La fonction tekpixel modifie la couleur d'un pixel à une position donnée.</br>
Elle est defénis comme suit:

```
void      tekpixel(t_bunny_pixelarray *pix, t_bunny_position *pos, t_color *color);
```
La fonction tekpixel peut changer la couler uniquement si les positions ne sont pas hors du pixelarray</br>
Si la position donnée est fausse, la fonction ne changera rien.
---
</br></br>

<font color="#A0522D">tekgui_load</font color="#A0522D">
---
</br></br>
La fonction tekgui_load lit les informations présentes dans le fichier ini et remplit la structure getgui.
Il faut appeler cette fonction avant toute autre fonction utilisant la structure tekgui.
tekgui_load est definie comme si-dessous
</br>
```
t_tekgui     tekgui_load(const char *filename);
```
</br>
En cas d'erreur, la fonction tekgui_load retourne NULL et un message s'affichera sur la sortie d'erreur.

------
</br></br><font color="#A0522D">tekgui_display</font color="#A0522D">
------
</br></br>
La fonction tekgui_display écrit toutes les données contenues dans la structure t_tekgui dans un pixelarray.</br>
**<font color="red">ATTENTION</font color="red"> : tekgui_display ne gère pas l'affichage, elle se contente de "remplir" le pixelarray**</br>
Pour afficher la window, il faut utiliser la fonction [<font color="#AFEEEE">display_window</font color="#AFEEEE">](./fonction-fr/#display_window).</br>
tekgui_display est définie comme si-dessous

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
La fonction display_window affiche la fenêtre avec toute la structure.

```
void      display_window(t_tekgui *tekgui);
```
</br></br>
Cette fonction affiche l'image, mais ne la remplit pas le pixelarray.</br>
Pour remplir l'image, il faut utiliser [<font color="#AFEEEE">tekgui_display</font color="#AFEEEE">](./fonction-fr/#tekgui_display)</br>

---
</br></br><font color="#A0522D">tekfunction</font color="#A0522D">
---
</br></br>
La fonction tekfunction prend en paramètre le nom d'une fonction et renvoie l'adresse de cette fonction.</br>
Elle est definie comme suit:

```
void      *tekfunction(const char *functname);
```
</br></br>
Si la fonction n'existe pas ou qu'une erreur s'est produite, tekfunction va renvoyer NULL.</br>

---
</br></br><font color="#A0522D">tektext</font color="#A0522D">
---
</br></br>
Cette fonction afficher du texte en haut à gauche du pixelarray.</br>
Elle prend en paramètre le pixelarray de destination, une chaine de caractère à copier, et un pixelarray contenant les caractères</br>
Elle est definie comme suit:

```
void tektext(t_bunny_pixelarray *out, const char *str, t_bunny_pixelarray *font_png);
```

---
</br></br><font color="#A0522D">tekgetpixel</font color="#A0522D">
---
</br></br>
La fonction tekgetpixel prend en paramètre la position d'un pixel et renvoie sa couleur.</br>
Elle est definie comme suit :</br>
```
t_color      tekgetpixel(t_bunny_pixelarray *, t_bunny_position *);
```

---
</br></br><font color="#A0522D">tekgui_stop</font color="#A0522D">
---
</br></br>
La fonction tekgui_stop libère la mémoire occupée par la librairie.</br>
Elle doit obligatoirement etre appelée a la fin du programme.</br>
```
void      tekgui_stop(t_tekgui *);
```

---
</br></br><font color="#A0522D">tekgui_max_ram</font color="#A0522D">
---
</br></br>
La fonction tekgui_max_ram prend en paramètre le fichier ini qui correspond au projet.</br>
Elle est definie comme suit :</br>
```
void    tekgui_max_ram(const char *name);
```

Elle définit le maximum de ram qui peut être utilisé par le programme.</br>
Il faut l'appeler au début du programme, avant [<U><font color="#AFEEEE">tekgui_load</font color="#AFEEEE"></U>](./fonction-fr/#tekgui_load)
