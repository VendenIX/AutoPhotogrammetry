# AutoPhotogrammetry

https://VendenIX.github.io/AutoPhotogrammetry

créer un dossier images dans media et avoir la vidéo dans media et faire la commande suivante :
ffmpeg -i video.mp4 -vf "fps=10" images/img%03d.png

cv mettre toutes les images de la vidéo dans le dossier images pour faire la photogrammétrie 



---

autre problème : la vidéo bouge de partout car je n'ai pas de stabilisateur professionnel donc faut retoucher la vidéo 

reperer le mouvement :
ffmpeg -i input.mp4 -vf vidstabdetect=shakiness=10:accuracy=15 -f null -
stabiliser : 
ffmpeg -i input.mp4 -vf vidstabtransform=smoothing=30:input="transforms.trf" -c:a copy output.mp4