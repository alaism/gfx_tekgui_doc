<font color="#A0522D">This is an example of a fonctional ini file.</br></br>
============
You can copy it and try to change some value to try the library.</br></br></font color="#A0522D">
============

```
[info]
name="bonjour"
height=800
width=800
color=200,200,200
max_ram=15

[window]
nbr_button=3
name_button=button1,button2,button3
nbr_textbox=2
name_textbox=textbox1,textbox2
nbr_checkbox=2
name_checkbox=checkbox1,checkbox2
nbr_picbox=2
name_picbox=picbox1,picbox2

[button1]
name="button1"
posx=0
posy=50
height=100
width=100
color=70,70,70
select_color=150,150,150
fct_to_call="button1"

[button2]
name="button_2_name"
posx=300
posy=300
height=50
width=200
color=255,255,255
select_color=150,150,150
fct_to_call="button2"

[button3]
name="button_3_name"
posx=0
posy=700
height=900
width=900
color=80,130,240
select_color=170,0,170
fct_to_call="button3"

[textbox1]
name="bonjour"
posx=300
posy=100
height=100
width=300
color=80,80,80
text="tektext2"

[textbox2]
name="tekbox2"
posx=500
posy=500
height=100
width=200
color=80,80,80
text="bonjour2"

[checkbox1]
name="checkbox1"
posx=700
posy=70
height=50
width=50
fct_to_call_check="check"
fct_to_call_not_check="not_check"

[checkbox2]
name="checkbox1"
posx=70
posy=500
height=100
width=100
fct_to_call_check="check"
fct_to_call_not_check="not_check"

[picbox1]
name="source/emoji6.png"
posx=100
posy=250

[picbox2]
name="source/piece.png"
posx=650
posy=320

```
