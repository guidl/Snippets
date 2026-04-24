pour changer des noms en masse de fichiers
`dir | rename-item -NewName {$_.name -replace "2020","BASE_2k20"}`

Pour exporter la liste d'un répertoire dans un fichier texte après avoir ouvert un terminal dans le bon répertoire
`tree /F | Out-File -append C:\Users\XXXX\Desktop\séries.txt`

script PowerShell qui va changer l'extension de tous les fichiers .jpg dans le répertoire courant en .txt:
`Get-ChildItem -Filter *.webp | Rename-Item -NewName { $_.Name -replace '\.webp$','.png' }`

