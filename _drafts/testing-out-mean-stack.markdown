http://mean.io/#!/

http://code.tutsplus.com/tutorials/introduction-to-the-mean-stack--cms-19918

"packaged oriented structure'
http://blog.mean.io/2014/06/extending-mean-io/

brew uodate
brew install mongodb

To have launchd start mongodb at login:
    ln -sfv /usr/local/opt/mongodb/*.plist ~/Library/LaunchAgents
Then to load mongodb now:
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mongodb.plist
Or, if you don't want/need launchctl, you can just run:
    mongod --config /usr/local/etc/mongod.conf