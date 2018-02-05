# Full Stacker Resources 2018
A collation of resources and hopefully some examples

## Animations

* Functional javascript animation/motion library
https://popmotion.io

## CSS3 and Vanilla JS

* Horizontal scroll
https://codepen.io/colinlord/post/horizontal-scrolling-containers

## Command Line

#### Pipes
https://quickleft.com/blog/command-line-tutorials-redirection-pipes/

#### Sed & Awk
https://quickleft.com/blog/command-line-tutorials-sed-awk/

```shell
### Finding stuff
ls -la > file.txt
awk '/findable_text/' ~/file.txt

### Replacing stuff
echo "how now brown cow" > ~/file.txt
sed s/ow/aagh/ ~/file.txt

### Replacing stuff at every occurrence
echo "how now brown cow" > ~/file.txt
sed s/ow/aagh/g ~/file.txt
```

#### Reinstall All PHP7 Packages
Especially when working Scotchbox

```bash
sudo apt-get install --reinstall `dpkg -l | grep 'ii  php7' | awk '{ printf($2" "); next}'`
sudo service apache2 restart
```
