### caad.xyz

**how to run in local**:  

```
bundle exec jekyll serve  
```

**how to write a post? **

To create a post, add a file to your `_posts` directory with the following format:

`YEAR-MONTH-DAY-title.MARKUP`  

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. For example, the following are examples of valid post filenames:

```
2011-12-31-new-years-eve-is-awesome.md
2012-09-12-how-to-write-a-blog.md
```

All blog post files must begin with front matter which is typically used to set a layout or other meta data. For a simple example this can just be empty:

```
---
layout: post
title:  "Welcome to Jekyll!"
---

# Welcome

**Hello world**, this is my first Jekyll blog post.

I hope you like it!
ProT
```

Done!