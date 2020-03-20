<h1 align="center" style="box-shadow: 10px 5px 5px red">Compte rendu TP4</h1>                                   
<p>RIOUAL Matthieu :computer:</p>
<p>MORNEAU Hugo :computer:</P>

## Exercice 1

1) On créé son disque dur virtuel sur VirtualBox.

2) On voit notre nouveau disque avec ```lsblk``` où l'on voit le nouveau disque sdb de 5Go.

3) On créer notre partition, un secteur fait 512 bytes, il nous en faut donc 4000000 pour 2Go et 6000000 pour 3. On passe la deuxième au type NTFS.

4) On créé les systèmes de fichier avec ```mkfs /dev/sdb1``` et ```mkfs /dev/sdb2```.

5) ```df -T``` n'affiche pas notre disque car celui-ci n'est pas monté.

6) 