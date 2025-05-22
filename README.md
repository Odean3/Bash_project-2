# Bash_project-2

Automation with Bash and targeted file deletion
## 1- Deleting old file:

the bash script in the folder old_file_deletion is a tool that allows to delete older files when we specify how old they have to be in days, as in if days=4 then we will delete all files older than 2 days.
- I added a features where we have to input the number of days as an argument after we run the script in the directory we want to delete files in: 
```
bash ./del_oldfiles 4
```

## 2- Automating workspaces:

- in this project i tried to optimize my workspaces since they were getting quite cumbersome, i then had the idea to create bash scripts to either open or close these workspaces.
- for the record i currently have two workspaces: springboot and php.
### php:
for this workspace:
- I need to enable the xampp server to activate the sql and apche servers
- then i have to open vscode in /opt/lampp/htdocs directory
- finally i have to run obsidian 
for this particular workspace i made two scripts: **php0**(to launch all programs) and **xmp** an additional one to run superuser commands .
### springboot:
as for this workspace:
- i have to launch nvim in a springboot project directory of my choosing
- then i have to launch dbeaver(a database management util)
- after that is postman(for sending and receiving api requests)
- finally i have to run obsidian
for this workspace we first have **spring0** to run all programs and then **spring$** to shit down all the programs we have opened, thus ending our workspace session

## 3- Bonus
unless you'd like to bother with bash and points slashes, you'd want to automate this a bit and run it directly from the command line as you would with cd, ls ..
the way to do this is to add a path variable to the folder your scripts are at.

- first make sure your script is executable:
```
chmod u+r+x filename.sh
```

- navigate to the .bashrc file in your home directory and open it , go to the evry end and add this line:
```
export PATH=$PATH: /path/to/your/script/directory
```

save it and refresh the bashrc to update changes:

```
source ~/.bashrc
```

in case you want to run your script with root permissions, it would be better to separate the commands that needs root permissions from those that don't in separate files.
for the scripts that need root permission you *necessarily* have to move your scripts to the few directories that store the root permission scripts and commands:
```
/etc/sudoers
```
this file has the default directories where bash will look if you try to execute a file with root permissions.
- in my case i have the following:
```
Defaults        secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:>

```
