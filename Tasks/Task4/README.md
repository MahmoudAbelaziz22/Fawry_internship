# Task1:
write a bash script do this:\
    1- Detect OS distribution.\
    2- Based on OS distribution decide to use apt-get or yum to install docker.\
    3- clone custom wordpress website.\
    4- Run wordpress website with docker-compose.
## Flowchart:
```mermaid
flowchart TD
    start(Start) --> check_OS_distrib(Check OS distribution);
    check_OS_distrib --> 
    is_ubuntu{is Ubuntu or Debian?};
    is_ubuntu --> |Yes|Ubuntu_Debian_install(perform Install Docker using apt-get);
    is_ubuntu-->|NO|is_RH{is RedHat or CentOS};
    is_RH-->|Yes|RedHat_CentOS_install(Perform Install Docker using yum);
    RedHat_CentOS_install--> clone_wordpress_repo(Clone custom wordpress website);
    Ubuntu_Debian_install -->clone_wordpress_repo;
    is_RH-->|No|not_available(print not inlist OS distribution);
    not_available-->End(End);
    clone_wordpress_repo-->set_up_wordpress(Set up wordpress and Run it);
    set_up_wordpress-->End  
```
## How to Run the Script:
1- clone github repo to your local system:
```
git clone https://github.com/MahmoudAbelaziz22/Fawry_internship.git

```
2- change your current directory to task4 directory:
```
cd ./Fawry internship/Tasks/Task4
```
3- give excution permission to main.sh and helper-functions.sh files:

```
 chmod +x main.sh helper_functions.sh 
```
4- get your non root user:
```
USERNAME=$(whoami)
```
5- Run main.sh script, pass non root user, and enjoy ^_^ :
```
sudo ./main.sh "$USERNAME"
```
