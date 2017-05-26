# Σύνοψη

Η παρούσα αναφορά δημιουργήθηκε από τη φοιτήτρια Σμπιλίρη Παναγιώτα, με Α.Μ. Π2013130, στα πλαίσια του μαθήματος, 6ου εξαμήνου, "Τεχνολογία Λογισμικού". Σκοπός είναι η περιγραφή της εξαμηνιαίας εργασίας του μαθήματος, με αντικείμενο την επέκταση του παιχνιδιού Pacman -ένα HTML5 video game–. Για την εύρεση της εργασίας μπορείτε να ανακατευθυνθείτε στο [προσωπικό αποθετήριό](https://github.com/psbiliri/pacman) μου και για να παίξετε το παιχνίδι πατήστε [εδώ](https://psbiliri.github.io/pacman/).

# Εισαγωγή

Το Pacman είναι ένα arcade βιντεοπαίχνιδι της Namco το οποίο κυκλοφόρησε για πρώτη φορά στην Ιαπωνία, στις 22 Μαΐου, με τίτλο "Puck-Man".  Σχεδιαστής του παιχνιδιού είναι ο Toru Iwatani. Το όνομα Puck-Man προέρχεται από την ιαπωνική λέξη 'πακού' η οποία στα ιαπωνικά συμβολίζει το θόρυβο που κάνει κανείς ανοιγοκλείνοντας το στόμα του. Ωστόσο, τον Οκτώβριο του 1980, με την κυκλοφορία του στις Ηνωμένες Πολιτείες, το όνομά του άλλαξε σε Packman. <br>
Πηγή: ["Pac-man", Wikipedia](https://en.wikipedia.org/wiki/Pac-Man)

Καθώς το Pacman αποτελεί στις μέρες μας ένα κλασικό βιντεοπαιχνίδι, στα πλαίσια της εργασίας επιχειρήθηκε η ανανέωσή του με την προσθήκη σ'αυτό των χαρακτήρων ενός άλλου, αγαπημένου διαδρονικά, παιχνιδιού, του βιντεοπαιχνιδιού Super Mario.

# Επιλογή εργαλείων

Για την επέκταση του, HTML5 video game, Pacman χρησιμοποιήθηκε η βιβλιοθήκη [Phaser](https://phaser.io/) που διευκολύνει την ανάπτυξη παιχνιδιών μέσω HTML5. Η ανάπτυξη του κώδικα του παιχνιδιού, ο οποίος βρίσκεται στο αρχείο [index.html](https://github.com/psbiliri/pacman/blob/master/index.html), έγινε μέσω του Github και δεν χρησιμοποιήθηκε κάποιος επεξεργαστής κειμένου. Ωστόσο, για την κατασκευή της νέας πίστας χρησιμοποιήθηκε ως εργαλείο το λογισμικό [Tiled](http://www.mapeditor.org/).

# Διαδικασία ανάπτυξης

Στα πλαίσια του 1ου παραδοτέου, η μοναδική αλλαγή που πραγματοποιήθηκε στον δοθέντα κώδικα είναι η παρακάτω:
```
this.load.baseURL = 'https://psbiliri.github.io/pacman/';
```

Στα πλαίσια του 2ου παραδοτέου του μαθήματος, απ' όπου και ξεκίνησε ουσιαστικά η ανάπτυξη του παιχνιδιού, πραγματοποιήθηκε η αλλαγή του πρωταγωνιστή του παιχνιδιού, η προσθήκη επιπλέον αντικειμένων καθώς και η δημιουργία μιας νέας πίστας. Πιο συγκεκριμένα, ο πρωταγωνιστής Pacman αντικαταστάθηκε από τον Super Mario και οι αρχικές κουκίδες (dots) αντικαταστάθηκαν από κέρματα (coins). Επιπλέον, τη θέση της αρχικά δοθείσας πίστας πήρε μια νέα, με την ανατοποθέτηση των tiles του δοθέντος tileset στο χώρο της πίστας. Η νέα αυτή πίστα δημιουργήθηκε με τη χρήση του Tiled.

Για τις παραπάνω αλλαγές, "ανέβηκαν" τα κατάλληλα αρχεία στο φάκελο [assets](https://github.com/psbiliri/pacman/tree/master/assets) του αποθετηρίου του παιχνιδιού και "φορτώθηκαν" με τις κατάλληλες αλλαγές στον παρακάτω κώδικα:
```
this.load.image('dot', 'assets/coin.png');
this.load.image('tiles', 'assets/pacman-tiles.png');
this.load.spritesheet('pacman', 'assets/superMario.png', 32, 32);
this.load.tilemap('map', 'assets/superMario_pacman-map.json', null, Phaser.Tilemap.TILED_JSON);
```
...
```
this.map.addTilesetImage('pacman-tiles', 'tiles');
```

Ο πρωταγωνιστής και τα αντικείμενα που χρησιμοποιήθηκαν είναι:
<p align="center">
  <img src="http://icons.iconarchive.com/icons/ph03nyx/super-mario/128/Paper-Mario-icon.png">
  <img src="http://icons.iconarchive.com/icons/ph03nyx/super-mario/64/Question-Coin-icon.png">
</p>

Η νέα πίστα που δημιουργήθηκε είναι:
<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/17690864/26460038/1ba668b6-4181-11e7-91b8-d075535e02fe.png">
</p>

Στη συνέχεια, στα πλαίσια του 3ου παραδοτέου, το παιχνίδι προεκτάθηκε, αρχικά, με την προσθήκη score. Για την προσθήκη του score, προστέθηκε ο παρακάτω κώδικας:
```
var score = 0;
var scoreText;
```
...
```
scoreText = game.add.text(290, -5, 'Score: 0', {fond: '11px Verdara', fill: '#ffffff'})
```
...
```
score += 5;
scoreText.text = 'Score' + score;
```

# Διάγραμμα λειτουργίας συστήματος
# Ενδεικτικές οθόνες
# Συμπεράσματα
