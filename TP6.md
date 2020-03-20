<h1 align="center" style="box-shadow: 10px 5px 5px red">Compte rendu TP6</h1>                                   
<p>RIOUAL Matthieu :computer:</p>
<p>MORNEAU Hugo :computer:</P>

## Exercice 1

1) On créé son disque dur virtuel sur VirtualBox.

2) On voit notre nouveau disque avec ```lsblk``` où l'on voit le nouveau disque sdb de 5Go.

3) On créer notre partition, un secteur fait 512 bytes, il nous en faut donc 4000000 pour 2Go et 6000000 pour 3. On passe la deuxième au type NTFS.

4) On créé les systèmes de fichier avec ```mkfs /dev/sdb1``` et ```mkfs /dev/sdb2```.

5) ```df -T``` n'affiche pas notre disque car celui-ci n'est pas monté.

6) On va dans le fichier _/dev/etc/fstab_ et y ajoute les lignes:
```
/dev/sdb1 /data ext2 defaults 0 0
/dev/sdb2 /win  ext2 defaults 0 0
```
On force la configuration avec ```mount -a```

7) Après avoir redémarré la VM, on voit dans les répertoire _/data_ et _/win_ que le montage a bien été effectué.

8)

9)

## Exercice 2

1) Le fichier _50-curtin-settings.cfg_ n'est pas présent dans _/etc/default/grub.d_, seul _init-select.cfg_ y est. Ce fichier ne sert plus à rien dans la version courrante et sera suprrimé dans le futur.

2) On change ```GRUB_TIMEOUT_STYLE=menu``` et ```GRUB_TIMEOUT=10``` pour que le menu s'affiche pendant 10 secondes au démarrage.

3) On lance ```update-grub```pour mettre à jour le fichier de configuration final.

4) Le menu GRUB apparaît bien pendant 10 sec avant la sélection automatique de l'OS.

5) Pour changer la résolution de GRUB, on décommente ```GRUB_GFXMODE``` et met sa valeur à 1280x1024 (on obtient les valeurs possibles avec la commande ```vbeinfo``` sur le GRUB. Pour la résolution du linux, on ajoute la ligne ```GRUB_GFXPLAYLOAD_LINUX=1280x1024```.
On lance update-grub pour finaliser la configuration.

6) On installe le paquet avec ```sudo apt install grub2-splashimages```. On ajoute dans le fichier _grub_ la ligne ```GRUB_BACKGROUND=usr/share/images/Plasma-lamp.tga``` puis on met à jour.
