
### Git-lfs setup
We will be using [git-lfs](https://git-lfs.github.com/) to manage the images that are used for the practical work
  instructions
  
1 - Install it
```shell
$ brew install git-lfs
```

2 - Set it up to track png file and add the gitattributes file
```shell
$ git lfs track 'images'
# OR only png files with
$ git lfs track '*.png'
$ git add .gitattributes
```

3 - Check the files that git-lfs is tracking
```shell
$ git lfs ls-files
```