# kbmaestro-dbschema
Keyboard Maestro macro library for use with DbSchema.  Allows for rapid creation of DB ERP diagrams.

## Installation
Once Keyboard Maestro is installed, simply browse to the library file and double-click it.  The library file is located in...  

    [./files/DbSchema Tables.kmlibrary](https://raw.githubusercontent.com/FredLackey/kbmaestro-dbschema/master/files/DbSchema%20Tables.kmlibrary)

## Usage
This library allows for rapidly creating new tables, indexes, and foreign keys within a single DbSchema layout.  Currently, there are **over 100 commands** for rapidly creating columns, indexes, and foreign keys in your tables:  

![Keyboard Maestro](https://github.com/FredLackey/kbmaestro-dbschema/raw/master/docs/img/kbmaestro.png)

There isn't an actual "command line" in DbSchema, so the macros use the descritpion field of the "New Table" (or "Edit Table") dialog to kick things off.  Just type the needed command:

![DbSchema Commands](https://github.com/FredLackey/kbmaestro-dbschema/raw/master/docs/img/kbmaestro_commands.png)

## Important Requirement
**Your DbSchema diagram must be set to MySql as the target database.**  This was chosen to standardize on a single "starting point" for all diagrams.  However, **you may change database platforms once your diagram is complete**.

#### Why MySql  
DbSchema allows for easily switching from one database to another.  For example, if your project is designed in Database X (SQL Server, for example), you may easily switch it to Database Y (Postgres, MySql, MariaDb, etc.) by simply clicking your mouse.  DbSchema gracefully translates all of the datatypes, fields, and other assets.

-----

## Author

Fred Lackey  
[fred.lackey@gmail.com](mailto:fredlackey@gmail.com)  
[www.fredlackey.com](http://www.fredlackey.com)  