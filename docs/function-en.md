<U><font color="#A0522D">**Function in the library**</font color="#A0522D"></U>
========
</br></br>

<font color="#A0522D">tekpixel</font color="#A0522D">
---
</br></br>
The function tekpixel change the color of one pixel.</br>
The function is define as below:
```
void      tekpixel(t_bunny_pixelarray *pix, t_bunny_position *pos, t_color *color);
```
The function tekpixel can change the color only if the pixel is on the pixelarray.</br>
If not, it will do nothing.
---
</br></br>

<font color="#A0522D">tekgui_load</font color="#A0522D">
----
</br></br>
The tekgui_load function loads all informations from the ini file and completes the structure.</br>
You must call this function first to be able to use all others.</br>
tekgui_load is define as below:

```
t_tekgui     tekgui_load(const char *filename);
```
</br>
If an error is found, the function will return NULL and print an error.</br>

------
</br></br><font color="#A0522D">tekgui_display</font color="#A0522D">
------
</br></br>
The function tekgui_display write all the informations from the structure to the pixelarray.</br>
**<font color="red">Warning</font color="red"> : tekgui_display will not display the pixelarray, it will just complete it**</br>
If you want to display the window, you must call the fonction [<font color="#AFEEEE">display_window</font color="#AFEEEE">](./function-en/#display_window)</br>
tekgui_display is define as below:

```
void       tekgui_display(t_bunny_pixelarray *pix, t_tekgui *tekgui);
```
</br></br>
To do something more simply,  u can use the function like the example below
```
tekgui_display(tekgui->pix, tekgui);
```

-------
</br></br><font color="#A0522D">display_window</font color="#A0522D">
-------
</br></br>
The function display_window print the window.

```
void      display_window(t_tekgui *tekgui);
```

This function prints the pixelarray, but can not set it.
To set the pixelarray, you must use [<font color="#AFEEEE">tekgui_display</font color="#AFEEEE">](./function-en/#tekgui_display)</br>

---
</br></br><font color="#A0522D">tekfunction</font color="#A0522D">
---
</br></br>
tekfunction takes in parameter the name of a function and return the adresse of this function.</br>
tekfunction is define as below

```
void      *tekfunction(const char *functname);
```
</br></br>

If the function does not exist or an error happened, tekfunction will return NULL.</br>

---
</br></br><font color="#A0522D">tektext</font color="#A0522D">
---
</br></br>
This function print a string.</br>
tektext takes in parameter two pixelarray and a string to print.</br>
tektext is define as below :


```
void tektext(t_bunny_pixelarray *out, const char *str, t_bunny_pixelarray *font_png);
```

---
</br></br><font color="#A0522D">tekgetpixel</font color="#A0522D">
---
</br></br>

The function tekgetpixel takes a pixelarray and a position of a pixel and return his color.</br>
tekgetpixel is define as below :</br>
```
t_color     tekgetpixel(t_bunny_pixelarray *, t_bunny_position *);
```
---
</br></br><font color="#A0522D">tekgui_stop</font color="#A0522D">
---
</br></br>
The function tekgui_stop free the memory.</br>
The function must be called at the end of the program.</br>
The function is define ad below :
```
void      tekgui_stop(t_tekgui *);
```

---
</br></br><font color="#A0522D">tekgui_max_ram</font color="#A0522D">
---
</br></br>
The function tekgui_max_ram takes in parameter the ini file, and set the maximum ram as definite in the ini.</br>
tekgui_max_ram is definie as below :

```
void    tekgui_max_ram(const char *name);
```

You must call the function before [<U><font color="#AFEEEE">tekgui_load</font color="#AFEEEE"></U>](./fonction-fr/#tekgui_load)
