# MAX-USB_DMX
### Max USB ENTTEC DMX (and Server)

#### Convertie une matrice Jitter vers une liste DMX compatible


Ported depuis PD : source :: http://wiki.labomedia.org/index.php/Pure_Data_vs_Enttec_Pro

---
La décomposition du message ressemble à :




* 126 : indique le début d'un message (0x7E)
* 6 : indique que l'on veut envoyer une trame
* 2 : LSB du nombre de canaux DMX
* 0 : MSB du nombre de canaux DMX
* 0 : valeur de l'adresse DMX 0, non utilisé mais toujours présente dans une trame.
* $1 : valeur variable à envoyer à l'adresse DMX 1
* 231 : indique la fin du message (0xE7)

Pour envoyer une trame avec 512 adresses il faut donc composer un message de la sorte :

126 6 2 0 0 $1 231
