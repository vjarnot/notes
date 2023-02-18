### rsync (copy) files in parallel (2 threads here) with progress bar:
    find ./src -mindepth 1 -type d | xargs -d "\n" -P2 -I% rsync -Pah % ./dest
