<font color="#A0522D">This is an example of a C program.</br></br>
============
You can copy it and try to change some value to try the library.</br></br>
============

I expect you understand all liblapin function</br></font color="#A0522D">
---
</br></br>

```c
t_bunny_response	onclic(t_bunny_event_state state,
			               t_bunny_mousebutton button,
			               void *my_data)
{
  t_tekgui *tekgui;

  tekgui = my_data;
  if (button == BMB_LEFT && state == GO_DOWN)
    {
      tekgui->pos_on_click[0].x = tekgui->pos_mousse[0].x;
      tekgui->pos_on_click[0].y = tekgui->pos_mousse[0].y;
      tekgui->click = 1;
    }
  return (GO_ON);
}

t_bunny_response	key(t_bunny_event_state state,
			            t_bunny_keysym keysym,
			            void *my_data)
{
  t_tekgui		*tekgui;

  tekgui = my_data;
  (void) tekgui;
  if (keysym == BKS_ESCAPE && state == GO_DOWN)
    return (EXIT_ON_SUCCESS);
  if (state == GO_DOWN)
    tekgui->last_key = keysym;
  return (GO_ON);
}

t_bunny_response	fonction_loop(void	*my_data)
{
  t_tekgui	*tekgui;
  ptrfct	yolo;

  (void)yolo;
  tekgui = my_data;
  tekgui_display(tekgui->pix, tekgui);
  aff_window(tekgui);
  return (GO_ON);
}

int	main()
{
  t_tekgui	*tekgui;

  tekgui_max_ram("exemple.ini");
  tekgui = tekgui_load("exemple.ini");
  if (tekgui == NULL)
    return (-1);
  bunny_set_key_response(key);
  bunny_set_click_response(onclic);
  bunny_set_loop_main_function(&fonction_loop);
  bunny_loop(tekgui->win, 60, tekgui);
  tekgui_stop(tekgui);
  return (0);
}
```

Pour pouvrer le bon fonctionnnement des fonctions, vous devez aussi ajouter ses fonction:</br>
```
void	button1()
{
  my_putstr("je suis dans button 1\n");
}

void	button2()
{
  my_putstr("je suis dans button 2\n");
}

void	button3()
{
  my_putstr("je suis dans button 3\n");
}

void	check()
{
  my_putstr("Check\n");
}

void	not_check()
{
  my_putstr("uncheck\n");
}
```
