# backup

this is a simple backup setup that I use on my home server

`conf.d` contains files that have file glob lists in them, like `.gitignore`
files. `./run` then runs restic for each file in `conf.d` and backs up the file
list under the tag of the file name. if a file with the same name as in
`conf.d` exists in `pre.d` it gets run before restic, and the same goes for
`post.d` but it's after restic. `env` contains environment variables for
restic, and gets sourced by `backup`.

by default, only the last two backups are stored, and old ones get deleted.
this can be edited in `forget`.

systemd unit/timer files are included
