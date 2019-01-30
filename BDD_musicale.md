    Récupérer tous les albums:
SELECT*FROM albums;


    Récupérer tous les albums dont le titre contient "Great" :
SELECT*FROM albums WHERE title LIKE '%Great%';

    le nombre total d'albums contenus dans la base:
SELECT count(*)TotalCount FROM albums


    Supprimer tous les albums dont le nom contient "music" :
delete from albums where title like '%music%';



    Récupérer tous les albums écrits par AC/DC:
select * from albums inner join artists on artists.artistID  = albums.artistID where name = 'AC/DC';



    Récupérer tous les titres des albums de AC/DC:
select tracks.name,artists.name from albums inner join artists on artists.artistID  = albums.artistID inner join tracks on tracks.albumID = albums.albumID where artists.name = 'AC/DC';



    Récupérer la liste des titres de l'album "Let There Be Rock":
select * from albums inner join tracks on tracks.albumID = albums.albumID where title = 'Let There Be Rock';



    Afficher le prix de cet album ainsi que sa durée totale:
 select albums.title, sum(unitprice) as prix, sum(milliseconds) as duree from albums inner join tracks on tracks.albumID = albums.albumID where title = 'Let There Be Rock';



    Afficher le coût de l'intégralité de la discographie de "Deep Purple"
select artists.name, sum(tracks.unitprice) as valeur  from albums inner join artists on artists.artistID  = albums.artistID inner join tracks on tracks.albumID = albums.albumID where artists.name = 'Deep Purple';



    Créer l'album de ton artiste favori en base, en renseignant correctement les trois tables albums, artists et tracks
insert into 'artists'(name) values ('Lola');
insert into 'albums' (title,artistID) values ('azafady',276);
insert into 'tracks'(trackID,name,albumID,mediatypeID,genreID,composer,milliseconds,bytes,unitprice) values (3504,'azafady aminao',348,4,10,'Lola sy ny tariny',512324,3354214,1.55);



