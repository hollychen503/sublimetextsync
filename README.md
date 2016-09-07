#使用git在多台机器上同步sublime text的设置和插件

##package文件夹位置

windows: `C:\Users\[YourName]\AppData\Roaming\Sublime Text 3\Packages`
mac: ` /Users/HiroMac/Library/Application\ Support/Sublime\ Text\ 3/Packages`

有些文件/文件夹不需要同步，加入到.gitignore

```
Package Control.last-run
Package Control.ca-list
Package Control.ca-bundle
Package Control.system-ca-bundle
Package Control.cache/
Package Control.ca-certs/
```

在第一台电脑上
```
cd [package folder]/User/
git init
git add .
git commit -m "Initial"
git remote add origin [your git repo]
git push origin master
```

##这样就可以在其他电脑上clone这个repo了
```
cd [package folder]
mv User User.old
git clone [your git repo] User
```

##如果设置有了改变，再同步到repo里
```
cd [package folder]/User
git add -A
git commit -m "Update settings"
git push
```

##在其他电脑上同步
```
cd [package folder]/User
git pull
```
