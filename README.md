# What's this?

It's a demo repository to show how to use Git LFS (Git Large File Storage) with GitHub.

Note: files under `images/` are (presumably) large files tracked by Git LFS. They are originally from [unsplash.com](https://unsplash.com/s/photos/family?license=free) whose license allows redistribution.

## How it's maingained

(Assuming Git LFS is already installed on your system)

After `git init`, run:

```bash
git lfs track "*.jpg"
git add .gitattributes
git add images/
git commit -m "Add images tracked by Git LFS"
```

At this stage, `.gitattributes` will contain the line:

```text
*.jpg filter=lfs diff=lfs merge=lfs -text
```

This line tells Git to use the LFS filter for files matching the pattern `*.jpg`. The `-text` option indicates that these files should not be treated as text files, which is important for binary files like images.
