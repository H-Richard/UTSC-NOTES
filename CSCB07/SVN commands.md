## SVN commands

### "svn co"

the svn equivalent of git clone, usage

```bash
svn co https://markus.utsc.utoronto.ca/svn/cscb07s19/group_0001/
```

### "svn commit"

self explanatory, usage

```bash
svn commit -m 'init'
```

### "svn update"

pull command, usage


```bash
svn update https://markus.utsc.utoronto.ca/svn/cscb07s19/group_0001/
```

### "svn status"

checks local status, usage

```bash
svn status
```

### "svn add"

works like git add, will add a new file to be commited to svn repo, usage

```bash
svn add filename
svn commit -m 'filename'
```


###File Codes:

M - Modified, new local work but not updated.

U - Updated, no new local work since last revision.

G - Merged, new local work since last revision.

C - Conflicted, occurs when local work overlaps with updated server work. 

? - File unknown to svn server, unversioned file.
