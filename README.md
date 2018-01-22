# Full Stacker Resources 2018
A collation of resources and hopefully some examples

## Animations

* Functional javascript animation/motion library
https://popmotion.io

## Command Line

#### Pipes
https://quickleft.com/blog/command-line-tutorials-redirection-pipes/

#### Sed & Awk
https://quickleft.com/blog/command-line-tutorials-sed-awk/

```shell
### Finding stuff
ls -la > temp.txt
awk '/findable_text/' ~/file.txt

### Replacing stuff
echo "how now brown cow" > ~/temp.txt
sed s/ow/aagh/ ~/temp.txt

### Replacing stuff at every occurrence
echo "how now brown cow" > ~/temp.txt
sed s/ow/aagh/g ~/temp.txt
```
