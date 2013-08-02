deploy_script
=============

Simple deploy script for rails projects

A bash script that applies a zipped deploy to a Rails project.

To use:

* Rename deploy_script.cfg.example to deploy_script.cfg and modify as appropriate.
* Save files in /home/username/bin.
* Create a directory named deploy (or whatver value given to DEPLOYFOLDER) in /home/username.
* Rename and modify or delete deploy_script_symlinks.sh.example.
* Save a zip file to be deployed in deploy directory.
* Run deploy_script.

Steps:

1. Extract deploy archive to TEMPFOLDER
2. Archive live site to BACKUPFOLDER
3. Move deploy archive to ARCHIVEFOLDER
4. Remove certain files (e.g. database.yml) from TEMPFOLDER
5. Copy content of TEMPFOLDER to LIVEFOLDER
6. Recreate symlinks if they were lost by sourcing deploy_script_symlinks.sh
7. Clear TEMPFOLDER
8. Run rake tasks (e.g. to minify javascript)
9. Restart Phusion Passenger

