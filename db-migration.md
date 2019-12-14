* We can have a module, named "migration" instance of which, "migrator", which is responsible for all the db upgrade.
* While the application is starting, initialize migrator with dbConnection, and a absolute path of migration directory (where the migration scripts resides).
* Migrator on start will ensure that
  * it has initialized a directory "migrations" (if not found create it)
  * there is a document in a db collection "migration", which includes at least three fields
    * lastMigrationNumber : <some number which tells upto which number migration is already done in previous version of application>
    * isMigrating : <whether currently migration is going on> (this field is required to ensure that migration does not get started multiple nodes) so we will update this entry to true before starting the migration in one db transaction.
  * Migrator will take backup of database and keep somewhere on hardrive.
  * read the migrations directory, (we are already ensuring the migration scripts have some number like m000001.js m000002.js ... ) and find the document in db and find the lastMigrationNumber. eg if the lastMigarationNumber is 31, and we have files m000001.js ... m000031.js..m000032.js..m000033.js..m000034.js then migrator will run the last 3 scripts, one by one.
  * Every file has exported a fixed function say
    * exports.up = function(app, next){  // once all schema changes done, or other stuffs for migrations done then call this callback, callback if no error will call next migration script (handled by migrator) } and
    * exports.down = function(app, next) { // some logic to undo the changes in case failure in current migration happens.  }
      * this will be helpful in cases we need to downgrade the db, for some reasons.
      * We can take it as advance and good to have, but it is not compulsory.
  * make isMigrating flag false and goes off.
* We should ideally have "fixture" module separately to create empty directory and create init entry in db collection  "migrations"
