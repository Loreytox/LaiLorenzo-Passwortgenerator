# Portfolioeintrag
Lai Lorenzo

## Einleitung

In diesem PS1 Projekt handelt es sich, um ein Passwortgenerator.

## Was habe ich gelernt?

In diesem Projekt habe ich gelernt, wie man in PowerShell eine Bedingung prüft, ob eine Datei existiert, und falls nicht, eine neue Datei erstellt.

## Beschreibung

Um externe Dateien in PowerShell (.ps1) zu lesen und zu schreiben, kann ich den Befehl "Get-Content" verwenden, um den Inhalt einer Datei zu lesen, und den Befehl "Set-Content", um den Inhalt in eine Datei zu schreiben. Um eine Datei zu lesen, verwende ich "Get-Content -Path Pfad_zur_Datei", wobei "Pfad_zur_Datei" den tatsächlichen Pfad zur Datei darstellt. Um den Inhalt in eine Datei zu schreiben, verwendet man "Set-Content -Path Pfad_zur_Datei -Value 'Inhalt'", wobei "Pfad_zur_Datei" der Pfad zur Datei ist und 'Inhalt' der Text ist, der in die Datei geschrieben werden soll. Jedoch habe ich nicht "Set-Content -Path Pfad_zur_Datei -Value 'Inhalt'" benutzt. 

![grafik](https://github.com/Loreytox/LaiLorenzo-Passwortgenerator/assets/110893594/139c1d83-59ec-494d-b5e8-dc4b7c843750)

Um den Inhalt in eine andere Datei zu schreiben, habe ich den Befehl "$resultWithoutSpaces | Out-File -FilePath Pfad_zur_Zieldatei -Append" benutzt. Dabei wird der Inhalt, der in der Variable "$resultWithoutSpaces" gespeichert ist, an die Zieldatei angehängt. Der Parameter "-Append" sorgt dafür, dass der Inhalt am Ende der Zieldatei hinzugefügt wird, anstatt sie zu überschreiben.

Aber was wenn man eine neue Datei erstellen möchte? Zuerst frage ich den Benutzer nach dem Namen der TXT-Datei oder ob eine neue erstellt werden soll, indem ich den Befehl "$fileName = Read-Host "Geben Sie den Namen der TXT-Datei ein oder erstellen Sie eine neue (vorhandene TXT-Dateien: savedPass.txt)." verwenden.

Dann überprüfe ich mit dem Befehl "-not (Test-Path $fileName)", ob die angegebene Datei nicht existiert. Wenn dies der Fall ist, erstelle ich die Datei mit dem Befehl "$null = New-Item -Path $fileName -ItemType File" und gebe eine entsprechende Meldung aus: "Die neue TXT-Datei: $fileName wurde erstellt und das Passwort $resultWithoutSpaces wurde gespeichert."

Falls die Datei bereits existiert, füge ich das Passwort mit dem Befehl "$resultWithoutSpaces | Out-File -FilePath $fileName -Append" hinzu und gebe eine Meldung aus: "Passwort in $fileName gespeichert".

Auf diese Weise kann ich den Inhalt einer vorhandenen Datei mit "Get-Content" lesen und den Inhalt in eine andere Datei mit "$resultWithoutSpaces | Out-File" schreiben.

Alles ist durch diesem Code-Snippet möglich:

![grafik](https://github.com/Loreytox/LaiLorenzo-Passwortgenerator/assets/110893594/8c5bf724-0a9f-4f05-8fe7-6bd64685a7be)

Und hier ist noch alles in einem GIF:

![ezgif com-gif-to-mp4](https://github.com/Loreytox/LaiLorenzo-Passwortgenerator/assets/110893594/fc2d4458-7ae8-4fec-b574-9a05baa31654)

# Reflektion zum Arbeitsprozess

Gut gelaufen👍:
- Anpassung an diese neue Sprache
- Anwendung der neuen Befehle
- Ich konnte alles schnell verstehen und ausprobieren
- Die gesuchten Informationen und Code-Stücke waren gut verständlich

Nicht so gut gelaufen👎:

- Anwendung von Funktionen
- Das Verständnis, wie man in Dateien schreibt

Verbesserungsvorschlag:

Eine Verbesserung könnte sein, dem Benutzer eine klare Option anzubieten, um eine neue Datei zu erstellen, anstatt nach dem Namen der TXT-Datei zu fragen. Dies könnte die Benutzerfreundlichkeit erhöhen und potenzielle Fehler vermeiden.
