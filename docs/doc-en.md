<U><font color="#A0522D">**Usage of the library**</font color="#A0522D"></U>
===============
</br></br>
This manual is made for users who know how to use the following function :

```c
bunny_set_key_response();
bunny_set_loop_main_function();
bunny_loop();
```

------
</br></br><U><font color="#A0522D">Establishment of an ini file</font color="#A0522D"></U>
------
</br></br>
The tekgui library needs a ini file to work.</br>
This is necessary to create a good one.</br>
Some part of the ini file are mandatory, some other are customizable.</br>
The ini file must be set like the following example.</br>
If not, some function of the library will return NULL and print an Error.

</br></br>
Example :

```
[info]
name="window"
height=800
width=800
color=200,200,200
max_ram=15
```
</br>
The domain `[info]` is a mandatory field.</br>
The domain `window` contains the name of the window made by the library.</br>
The domain `height` and `width` contains the height and the width of the window.</br>
The domain `color` contains the color of the window.</br>
The domain `max_ram` contains the maximum of ram usable by the program.</br></br>
If you see <font color="RED">*Error: error in malloc*</font color="RED"> print on the terminal, it's probably because `max_ram` is too short.</br>
If window, color, height or width is empty or miss, the function will return an error.</br>

------
</br></br><U><font color="#A0522D">Initialization of the ini file</font color="#A0522D"></U>
------
</br></br>
This part is used to load the ini informations and set the tekgui structure.
</br></br>
Example :

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
The domain `[window]` is a mandatory field.</br>
The domain `nbr_button` is the number of button in the window.</br>
The domain `name_button` contains the name of all buttons. The number of name and `nbr_button` must match.</br>
The domain `nbr_textbox` is the number of textbox in the window.</br>
The domain `name_textbox` contains the name of all textbox. The number of name and `nbr_text` must match.</br>
The domain `nbr_checkbox` is the number of checkbox in the window.</br>
The domain `name_checkbox` contains the name of all checkbox. The number of name and `nbr_checkbox` must match.</br>
The domain `nbr_picbox` is the number of picbox in the window.</br>
The domain `name_picbox` contain the name of all picbox. The number of name and `nbr_checkbox` must match.</br></br>
__WARNING__ All the domains must be set.</br>
If, for example, you don't want checkbox in you interface, you should do :

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
</br></br><U><font color="#A0522D">Button setup</font color="#A0522D"></U>
-----
</br></br>
Each button must be define as below :
</br></br>
Example :

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
The domain `[button1]` contains the name of the button to set, surrounded by [ ].</br>
The domain `name` contains the name of button in the window.</br>
The domain `posx` and `posy` contains the starting position of the button.</br>
The domain `height` and `width` defines the size of the button.</br>
The domain `color` contains the color of the button.</br>
The domain `select_color` is the color when the mousse is on the button.</br>
The domain `fct_to_call` contains the name of the function to call when you clock on the button.</br></br>
Each button must have is own setup.</br>
If there is two different setup for the same button, the program will only use the first one.

-----
</br></br><U><font color="#A0522D">Textbox setup</font color="#A0522D"></U>
-----
</br></br>
Each textbox must be define as below :
</br></br>
Example :

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
The domain `[textbox1]` contains the name of the textbox, surrounded by [ ].</br>
The domain `name` contains the name of the textbox. The name will not be print on the window.</br>
The domain `posx` and `posy` defines the starting position of the textbox.</br>
The domain `height` and `width` defines the size if the textbox.</br>
The domain `color` contains the color of the textbox.</br>
The domain `text` contains the initial string print in the textbox</br></br>
Each textbox must have is own setup.</br>
If there is two different setup for the same textbox, the program will only use the first one.</br>
To use the textbox, you just have to click on it.</br>
Only the alphabetical character, the space and delete can be use in textbox.</br>
The others character will have no effect.</br>
</br>

-----
</br></br><U><font color="#A0522D">Checkbox setup</font color="#A0522D"></U>
-----
</br></br>
Each checkbox must be define as below :
</br></br>
Example :

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
The domain `[checkbox1]` contains the name of the Checkbox, surrounded by [ ].</br>
The domain `name` contains the name of the checkbox. The name will not be print on the window.</br>
The domain `posx` and `posy` defines the starting position of the checkbox.</br>
The domain `height` and `width` defines the size if the checkbox.</br>
The domain `fct_to_call_check` contains the name of the function to call when the checkbox is check.</br>
The domain `fct_to_call_not_check` contains the name of the function to call when the checkbox is uncheck.</br>
</br>
Each checkbox must have is own setup.</br>
If there is two different setup for the same checkbox, the program will only use the first one.</br>
</br>

-----
</br></br><U><font color="#A0522D">picbox setup</font color="#A0522D"></U>
-----
</br></br>
picbox mean picture box.</br>
Each picbox must be define as below.</br>
</br></br>
Example :

```ini
[picbox1]
name="emoji6.png"
posx=100
posy=250
```
</br>
The domain `[picbox1]` contains the name of the picbox, surrounded by [ ].</br>
The domain `name` contains the link of the picture.</br>
The domain `posx` and `posy` contains the starting position of the picture.</br>
</br>
Each picbox must have is own setup.</br>
If there is two different setup for the same checkbox, the program will only use the first one.</br>
The picture will be print from the starting position to the end.</br>
If the end of the picture is out of the window, an error will be print.</br>
Name must contain the link to the picture, or the function will retrun an error.</br>
If the picture not exist, or the link is false, the function will retrun an error.</br>
</br>

-----
</br></br><U><font color="#A0522D">Help</font color="#A0522D"></U>
-----
To try the library, you can use [<U><font color="#AFEEEE">this ini file</font color="#AFEEEE"></U>](./exemple-ini.md)</br>
If you need a C program, you can use [<U><font color="#AFEEEE">mine</font color="#AFEEEE"></U>](./basic-c-program.md)</br></br></br>
---
</br></br><U><font color="#A0522D">function in the library</font color="#A0522D"></U>
---

All the function implement in the library are [<font color="#AFEEEE">here</font color="#AFEEEE">](./function-en)

If you are looking for a specific function, you can click on the following link :
</br>
</br>
1. [<U><font color="#AFEEEE">tekgui_load</font color="#AFEEEE"></U>](./function-en/#tekgui_load)</br>
2. [<U><font color="#AFEEEE">tekgui_display</font color="#AFEEEE"></U>](./function-en/#tekgui_display)</br>
3. [<U><font color="#AFEEEE">display_window</font color="#AFEEEE"></u>](./function-en/#display_window)</br>
4. [<U><font color="#AFEEEE">tekpixel</font color="#AFEEEE"></U>](./function-en/#tekpixel)</br>
5. [<U><font color="#AFEEEE">tekfunction</font color="#AFEEEE"></U>](./function-en/#tekfunction)</br>
6. [<U><font color="#AFEEEE">tektext</font color="#AFEEEE"></U>](./function-en/#tektext)</br>
7. [<U><font color="#AFEEEE">tekgetpixel</font color="#AFEEEE"></U>](./function-en/#tekgetpixel)</br>
8. [<U><font color="#AFEEEE">tekgui_stop</font color="#AFEEEE"></U>](./function-en/#tekgui_stop)</br>
9. [<U><font color="#AFEEEE">tekgui_max_ram</font color="#AFEEEE"></U>](./fonction-en/#tekgui_max_ram)</br>
