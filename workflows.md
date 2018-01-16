### Git by Workflow
### Restore a deleted file
1) Use a "delete" commit:
```
git log | grep -i delete  // find commit sha
git log --name-only  <sha> // find file path
git checkout <sha>^ -- <filepath> // ^ means the commit just before that one
```

2) If you remember the file path, it's easy:
```
git checkout <sha> -- <filepath>
```

3) If you don't remember exactly the file name, it's a bit trickier with pattern matching:
```
git log --all --full-history --name-only --pretty=format: master -- server/__tests__/**.js
```
