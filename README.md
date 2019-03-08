# sample_peco_apt
peco + apt  
https://github.com/peco/peco/wiki/Sample-Usage#peco--apt

```
function iapt() {
    if [ -z "$1" ]; then
        echo "Usage: iapt <initial search string> - select packages on peco and they will be installed" 
    else 
        sudo apt-cache search $1 | peco | awk '{ print $1 }' | tr "\n" " " | xargs -- sudo apt-get -y install
    fi  
}
```
![sample](https://raw.githubusercontent.com/tsaeki/sample_peco_apt/master/20190309_iapt_cut.gif)
