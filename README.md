# Intro to SQL

1.  Install the SQLite Browser if you haven't already [here](http://sqlitebrowser.org/)
2.  Open the SQLite Browser and click 'File -> Open DataBase'
3.  Choose the `chinook.db` file from this repo. This database is open source and maintained by Microsoft (SQL is no fun if you don't have any data)
4.  Click the tab that says 'Execute SQL'. Type SQL queries in the box above. Press the play button. See the results of that query in the box below

## Challenges

1.  Write the SQL to return all of the rows in the artists table?

```SQL
SELECT * FROM artists;
```

2.  Write the SQL to select the artist with the name "Black Sabbath"

```SQL
SELECT * FROM artists WHERE name="Black Sabbath";
```
SELECT * FROM artists WHERE name LIKE "%Black%";

3.  Write the SQL to create a table named 'fans' with an autoincrementing ID that's a primary key and a name field of type text

```sql
CREATE TABLE fans(id INTEGER PRIMARY KEY, name STRING);
```

4.  Write the SQL to alter the fans table to have a artist_id column type integer?

```sql
ALTER TABLE fans ADD COLUMN artist_id INTEGER;
```

5.  Write the SQL to add yourself as a fan of the Black Eyed Peas? ArtistId **169**

```sql
INSERT INTO fans (name, artist_id) VALUES ("Sarah", 169);
```

6.  Check out the [Faker gem](https://github.com/stympy/faker). `gem install faker`, open up irb, run `require 'faker'` and then generate a fake name for yourself using `Faker::Name.name`. How would you update your name in the fans table to be your new name?

    ```sql
    UPDATE fans SET name="Earlean Bohm" WHERE name="Cernan";
    ```

7.  Write the SQL to delete your row in the fans table.

```sql
DELETE FROM fans WHERE name="Cernan";
```

8.  Write the SQL to return fans that are not fans of the black eyed peas.

```sql
SELECT * FROM fans WHERE artist_id IS NOT 169;
```
