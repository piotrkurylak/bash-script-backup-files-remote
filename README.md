# bash-script-backup-files
Bash script which allows to create compressed archive.

# Requirements
Due to create lock file you have to have superuser privileges.

# Variables
Name of lock file.
````bash
lock_file_name="${0}.lock"
````

Directory where to store lock file.
````bash
lock_file_path="/var/lock/"
````

Full lock file path.
````bash
lock_file="${lock_file_path}${lock_file_name}"
````

Directory to backup.
````bash
backup_dir="${1}"
````

Suffix of backup file name.
````bash
backup_file_name="backup.tar.gz"
````

Full name of backup.
````bash
backup_full_name="$(date +%F-%H-%M)"."${backup_file_name}"
````

Identity file, selects the file from which the identity (private key) for public key authentication is read.
````bash
identity_file="${2}"
````

User who will be used to connect to remote machine.
````bash
username="${3}"
````

Ip address of remote machine. 
````bash
remote_ip="${4}"
````

Remote destination where to transfer files.
````bash
remote_dest=${5}
````

# How to use it?
````bash
sudo ./backup_files.sh [FILE/DIR] [IDENTITY FILE] [USERNAME] [REMOTE IP] [REMOTE DESTINATION] 
````

# Example
````bash
sudo ./backup_files.sh /tmp /path/Key.pem username 10.0.1.2 /path/backup 
````



