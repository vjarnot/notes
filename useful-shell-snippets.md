### rsync files in parallel (2 threads here) with progress bar NB: careful with nested directories, it's possible to tell rsync to copy both the parent and child directories, which is no bueno, since rsync traverses down on its own:
    find ./src -mindepth 1 -type d | xargs -d "\n" -P2 -I% rsync -Pah % ./dest

### rsync perms fix for TrueNAS:
    rsync -Pah --no-perms src/ dest

### 7-Zip extract, but skip certain file extensions (\*.json in this example):
    7z x '-xr!*.json' .\src.zip -o/dest-folder

### TrueNAS SCALE HBA temps:
    storcli show all
    storcli /c0 show all |grep temp

### iperf3 client command (60 seconds, 4 threads):
    iperf3 -c 10.x.x.x --bidir -t 60 -P 4
