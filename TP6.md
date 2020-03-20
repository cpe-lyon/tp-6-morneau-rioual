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

7) Après avoir redémaré la VM, on voit dans les répertoire _/data_ et _/win_ que le montage a bien été effectué.

8)

9)

## Exercice 2

1) 
