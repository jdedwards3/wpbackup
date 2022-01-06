# WordPress backup

## Usage

First make the script executable:

```
chmod +x ./wpbackup
```

Then use it like this:

```
./wpbackup -u user -h host -f folder
```

This script uses the WP CLI, and does not require that WP CLI is installed on your local computer. It does require that WP CLI is installed on the remote host.

This script will attempt to find a WordPress installation based on the specified folder.

If WordPress is found, maintenance mode will be activated. The site folder will then be archived and compressed into a file with the pattern:

```
backup_${timestamp}_${folder}.tar.gz
```

Then the WordPress database will be exported saved as a compressed file with the pattern:

```
backup_${stamp}_${folder}-db.sql.gz
```

Maintenance mode will then be deactivated.

Both the files and database are saved to the local computer where this script is run, not the remote host.
