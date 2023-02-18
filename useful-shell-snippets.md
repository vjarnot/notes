### rsync (i.e., copy) files in parallel (this does 2 threads):
    find ./src -mindepth 1 -type d | xargs -d "\n" -P2 -I% rsync -Pah % ./dest
