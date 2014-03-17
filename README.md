mark2 backup
============

Bash script to backup mark2 based Minecraft servers CPU and I/O friendly.

# Commands

    m2backup backup <world>            Backup the server.
    m2backup list [world]              List current incremental backups.
    -debug                             Enable debug output (Must be the last argument).

# Configuration

As you might see, this script creates a configration file in your `$HOME folder.  

Make sure you made all adjustments as your needs for the following variables:

* `MARK2NAME`
* `SERVERDIR`
* `BACKUPDIR`
* `WORLDS`
* `EXCLUDES`

You can also override:

* `RUNBACKUP_NICE` (`${BIN_NICE} -n19` by default)
* `RUNBACKUP_IONICE` (`${BIN_IONICE} -c 3` by default)
* `TIMESTAMP` (`$(date +"%Y-%m-%d-00-00")` by default)
* `ANNOUNCE` (`false` by default)
* `SAY_BACKUP_START` (`Backup started...` by default)
* `SAY_BACKUP_FINISHED` (`Backup successfully finished.` by default)

# Installation

## Bash script

    cd /usr/local/src
    git clone https://github.com/frdmn/mark2-backup.git
    ln -s /usr/local/src/mark2-backup/m2backup /usr/bin/m2backup
    chmod a+x /usr/bin/m2backup
    mkdir -p /opt/backups/minecraft
    chown -R $RUNUSER /opt/backups

## Create default configuration files

	m2backup

# Dependencies

You need `nice`, `ionice`, `tar` and `mark2` to use all features of minebackup.sh:

* `apt-get install nice ionice tar`
* https://mark2.io/install
