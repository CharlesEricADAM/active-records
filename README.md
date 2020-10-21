# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

a) Niveau facile
Quel est le nombre total d'objets Album contenus dans la base (sans regarder les id bien sûr) ?
```ruby
Album.count
```
* Qui est l'auteur de la chanson "White Room" ?
```ruby
Track.find_by(title: "White Room").artist
```
* Quelle chanson dure exactement 188133 milliseconds ?
```ruby
Track.find_by(duration: 188133).title
```
* Quel groupe a sorti l'album "Use Your Illusion II" ?
```ruby
Album.find_by(title: "Use Your Illusion II").artist
```

b) Niveau Moyen
* Combien y a t'il d'albums dont le titre contient "Great" ? (indice)
```ruby
Album.where("title like ?", "%Great%").count
```
* Supprime tous les albums dont le nom contient "music".
```ruby
Album.where("title like ?", "%music%").destroy_all
```
* Combien y a t'il d'albums écrits par AC/DC ?
```ruby
Album.where(artist: "AC/DC").count
```
* Combien de chanson durent exactement 158589 millisecondes ?
```ruby
Track.where(duration: 158589).count
```

c) Niveau Difficile
Pour ces questions, tu vas devoir effectuer des boucles dans la console Rails. C'est peu commun mais c'est faisable, tout comme dans IRB.

* puts en console tous les titres de AC/DC.
```ruby
Track.where(artist: "AC/DC").each {|a| puts a.title}
```
* puts en console tous les titres de l'album "Let There Be Rock".
```ruby
Track.where(album: "Let There Be Rock").each {|a| puts a.title}
```
* Calcule le prix total de cet album ainsi que sa durée totale.
```ruby
Track.where(album: "Let There Be Rock").map {|a| a.price}.sum
```
Calcule le coût de l'intégralité de la discographie de "Deep Purple".
Modifie (via une boucle) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist.


* ...
