# Useful Linux commands
Some Linux commands I like

- Redo last command as root: ```sudo !!```
- Leave the process even if terminal is closed, no log: ```nohup command >/dev/null 2>&1 &```
- Exit terminal without killing actual processes, something if forgot about nohup: ``` disown -a && exit```
- Skip the command from the history -> put space in the beginning of the command
- Fix last command in the editor: ```fc```
- Mount a fast ram disk:
```
mkdir -p /mnt/ramdisk
mount -t tmpfs tmpfs /mnt/ramdisk -o size=2048M
```
- Create a folder structure quickly: ```mkdir -p folder/{subdir1,subdir2}/{sub1,sub2,sub3}```
- Open editor to run a command: ctrl+x+e
- Run a Python server on a port to share the folder via www: ```python3 -m http.server ${port}```
- Get structure of drives: ```lsblk```
- Remount root / with rw: ```mount -o remount,rw /```
- Replace text in path: ```find . -type f | xargs sed -i "s/$old/$new/g"```
- General fix of permissions:
```
find . -type d | xargs chmod 755
find . -type f | xargs chmod 644
```
- Get output from a columns: ```awk '{print $2}'``` or ```tr -s "$delimiter" | cut -d "$delimiter" -f $column``` where delimiter can be i.e. a space and column i.e. 3  
- Write image to a drive, i.e. Linux img to USB: ```sudo dd if=$img_file of=/dev/$disk_number bs=4M && sync```
