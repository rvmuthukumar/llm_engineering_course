
# On AWS Linux
## to check disk usage
df -h

## to grow the disk to use all available space in the volume
## first grow the partiion
sudo growpart /dev/nvme0n1 1
## next grow the file system if needed
sudo xfs_growfs -d /

## for using a temp folder for pip to download and store install files temporarily
## You need to tell pip to use your spacious home directory for temporary files instead of the small /tmp folder.
### ~ = home dir, -p flag ensures that both the environment and the tmp folders are created
mkdir -p ~/environment/tmp
### This command sets an environment variable that tells pip: "Don't use the small system /tmp folder. Use this specific folder I just
TMPDIR=~/environment/tmp pip install --no-cache-dir -r requirements.txt

# Win setup steps

## since i had multiple python versions
- py -3.11 -m venv llms
- llms\scripts\activate
- (llms) C:\Source Code\course\llm_engineering_course>python --version
   >>Python 3.11.7



