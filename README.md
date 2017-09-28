# kbmaestro-dbschema
Keyboard Maestro macro library for use with DbSchema.  Allows for rapid creation of DB ERP diagrams.

## Dependencies  
You must have both of the following tools installed to make use of this project:

[Keyboard Maestro](https://www.keyboardmaestro.com)  
[DbSchema](https://www.dbschema.com/)  

## Installation
Once Keyboard Maestro is installed, simply browse to the library file and double-click it.  The library file is located in...  

[./files/DbSchema Tables.kmlibrary](https://raw.githubusercontent.com/FredLackey/kbmaestro-dbschema/master/files/DbSchema%20Tables.kmlibrary)

## Usage
This library allows for rapidly creating new tables, indexes, and foreign keys within a single DbSchema layout.  Currently, there are **over 100 commands** for rapidly creating columns, indexes, and foreign keys in your tables:  

![Keyboard Maestro](https://github.com/FredLackey/kbmaestro-dbschema/raw/master/docs/img/kbmaestro.png)

There isn't an actual "command line" in DbSchema, so the macros use the descritpion field of the "New Table" (or "Edit Table") dialog to kick things off.  Just type the needed command:

![DbSchema Commands](https://github.com/FredLackey/kbmaestro-dbschema/raw/master/docs/img/kbmaestro_commands.png)

## Command Syntax
Each command is split up in 1-3 parts.  For example, to create a field with a specific data type and length, the command is:

`<DATA TYPE ABBREVIATION><LENGTH><NULLABLE FLAG><SPACE>`

So, to create a `varchar(255)` column, you would type either `vc255` or `vc255n` (for nullable)

***Remember, a single space must follow your command to show it is complete.***

## Available Commands

### Simple Field Types  
You will be prompted for a field name unless otherwise specified:  

* `idNNN` : `char(NNN) PRIMARY KEY` (name of field is `id`, valid lengths: 1, 2, 3, 32)
* `pidNNN` or `pidNNNn` : `char(NNN)` (valid lengths: 1, 2, 3, 32)

### Primative Field Types  
You will be prompted for a field name:  

* `b` or `bn` : `boolean`
* `cNNN` or `cNNNn` : `char(NNN)` (valid lengths: 1, 2, 3, 5, 10, 20, 30, 50, 100, 200)
* `d` or `dn` : `datetime`
* `f` or `fn` : `float`
* `i` or `in` : `integer`
* `vcNNN` or `vcNNNn` : `varchar(NNN)` (valid lengths: 1, 2, 3, 5, 10, 20, 30, 50, 100, 200)

### Function Commands
Perform multi-step actions.  

* `fk` : Create foreign key on current table.  Prompts for local field name and primary table name.
* `idx` : Create single or multi-column index on current table.  Prompts for field name(s).
* `uidx` : Create single or multi-column **unique** index on current table.  Prompts for field name(s).

## Important Requirement
**Your DbSchema diagram must be set to MySql as the target database.**  This was chosen to standardize on a single "starting point" for all diagrams.  However, **you may change database platforms once your diagram is complete**.

#### Why MySql?  
DbSchema allows for easily switching from one database to another.  For example, if your project is designed in Database X (SQL Server, for example), you may easily switch it to Database Y (Postgres, MySql, MariaDb, etc.) by simply clicking your mouse.  DbSchema gracefully translates all of the datatypes, fields, and other assets.  MySql was chosen since it is widely used on all major operating systems.

-----

## Author

Fred Lackey  
[fred.lackey@gmail.com](mailto:fredlackey@gmail.com)  
[www.fredlackey.com](http://www.fredlackey.com)  