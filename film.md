

Sujet
- - - - X


Exo 1 Nom et année de naissance des artistes nés avant 1950.
    --REp: SELECT * FROM `artiste` 
                WHERE annéeNaiss < 1950;

Exo 2 Titre de tous les drames.
    --Rep: SELECT titre 
                FROM film where genre ='drames';

Exo 3 Quels rôles a joué Bruce Willis.
    --Rep: SELECT * 
                FROM artiste, 
                film, role WHERE role.idActeur = artiste.idArtiste 
                AND role.idFilm = role.idActeur AND artiste.nom = "willis" 
                AND artiste.prénom = "bruce";

Exo 4 Qui est le réalisateur de Memento.
    --Rep: SELECT * 
                FROM film , artiste, role where 
                role.idActteur = role.idFilm and
                film.idFilm = film.idRéalisateur and 
                role.idActeur = artiste.idArtiste
                and film.titre = "memento"; 

Exo 5 Quelles sont les notes obtenues par le film Fargo.
    --Rep: SELECT note 
                FROM notation, film where film.idFilm = notation.idFilm and
                film.titre = "fargo";

Exo 6 Qui a joué le rôle de Chewbacca?
    --Rep: SELECT DISTINCT artiste.nom, artiste.prénom
                FROM Role, Artiste, Film
                WHERE Role.idActor = Artiste.idActrice
                AND role.idFilm = Film.idFilm
                AND role.nomRôle = "Chewbacca";

Exo 7 Dans quels films Bruce Willis a-t-il joué le rôle de John McClane
?
    --Rep: SELECT film.titre
                FROM Role, Artiste, Film
                WHERE Role.idActeur = Artiste.idArtiste
                AND Role, idFilm = Film. idFilm
                AND role.nomRôle = 'John McClane'
                AND artiste.nom = 'Willis'
                AND artiste.prénom = 'Bruce' ;

Exo 8 Nom des acteurs de 'Sueurs froides'.
    --Rep:      ELECT artiste.nom, artiste.prénom
                    FROM role, artiste, film
                    WHERE role.idfilm = film.idFilm
                    ANd Role, idActeur = artiste. idArtiste
                    AND film.titre = 'Sueurs froides'

Exo 9 Quelles sont les films notés par l'internaute Prénom 0 Nom0.
    --Rep:      ELECT *
                    FROM internaute, film, notation
                    WHERE hotation.email = internaute. email
                    AND notation.idFilm = film.idFilm
                    AND internaute.nom = 'Nom0'
                    AND internaute .prénom = 'Prénom0';

Exo 10: Films dont le réalisateur est Tim Burton, et l’un des acteurs
Johnny Depp.
    --Rep:      SELECT film.titre
                    FROM artiste, film, role
                    WHERE role.idFilm = film.idFilm
                    AND film.idRéalisateur IN (
                        SELECT film.idRéalisateur
                        FROM film
                        WHERE artiste.nom = "Burton" AND artiste.prénom = 
                        "Tim"
                    );

Exo 11: Titre des films dans lesquels a joué ́Woody Allen. Donner aussi
le rôle.
    --Rep:      SELECT film.titre, role.nomRôle
                    FROM artiste, film, role
                    WHERE role.idActeur = article.idArtiste
                    AND role.idFilm = film.idFilm
                    AND artiste.nom = "Allen" AND artiste.prénom = "Woody";

Exo 12: Quel metteur en scène a tourné dans ses propres films ? Donner
le nom, le rôle et le titre des films.
    --Rep:      SELECT artiste.nom, artiste.prénom, role.nomRôle,
                    FROM artiste, film, role
                    WHERE role.idActeur = artiste.idArtiste
                    AND role.idFilm = film.idFilm
                    AND artiste.idArtiste = film.idRéalisateur;

Exo 13 Titre des films de Quentin Tarantino dans lesquels il n’a pas
joué.
    --Rep:

Exo 14 Quel metteur en scène a tourné ́en tant qu’acteur ? Donner le
nom, le rôle et le titre des films dans lesquels cet artiste a joué.
    --Rep:

Exo 15 Donnez les films de Hitchcock sans James Stewart.
    Rep:

Exo 16 Dans quels films le réalisateur a-t-il le même prénom que l’un
des interprètes ? (titre, nom du réalisateur, nom de l’interprète). Le
réalisateur et l’interprète ne doivent pas être la même personne.
    --Rep:

Exo 17 Les films sans rôle.
    --Rep:

Exo 18 Quelles sont les films non notés par l'internaute Prénom1 Nom1.
    --Rep:  SELECT *
                FROM film
                WHERE film.idFilm NOT IN (
                   SELECT film.idFilm
                      FROM internaute, film, notation
                      WHERE notation.email = internaute. email
                      AND notation.idFilm = film.idFilm
                      AND internaute.nom = 'Nom1'
                      AND internaute. prénom = 'Prénomi"
                );

Exo 19 Quels acteurs n’ont jamais réalisé de film ?
    --Rep:  SELECT *
                FROM artiste
                WHERE artiste.idArtiste NOT IN (
                SELECT film.idRéalisateur
                FROM film
                );

Exo 20 Quelle est la moyenne des notes de Memento.
    --Rep:  SELECT AVG(notation.note)
                FROM film, notation
                I WHERE film. idFilm = notation. idFilm
                You, 14 minutes ago
                AND film.titre = 'Memento';

Exo 21 id, nom et prénom des réalisateurs, et nombre de films qu’ils
ont tournés.
    --Rep:

Exo 22 Nom et prénom des réalisateurs qui ont tourné au moins deux
films.
    --Rep:

Exo 23 Quels films ont une moyenne des notes supérieure à 7.
    --Rep: 