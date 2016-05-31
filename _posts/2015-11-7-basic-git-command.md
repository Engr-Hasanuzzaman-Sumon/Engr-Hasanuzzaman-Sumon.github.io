---
layout: post
title:  "Basic git command"
date:   2015-11-7 2:44:00
categories: git
subcategory: beginner
comments: true
---

# Display git log
Display git log information nicely
`git log --oneline --decorate --graph`


where `oneline` show commit in one line, `--decorate` give some color and
`--graph` gives graph show.


# Display git branches
* Show all locals and remote branchs
`git branch -a`

* Show all locals branchs only
`git branch`

* Show all remote branchs only
`git branch -r`

# Remove/delete git branch
You can remove either local or remote branch

## Removing local branch
Let you want to delete your locale branch named `foo`
`git branch -d foo`

If branch `foo` have un merged commit then it need to force delete
`git branch -D foo`

## Removing remote branch
You can also use one of the following methods to delete the remote branch.
Let you want to delete remote branch `bar`
`git push --delete origin bar`

Which does the same thing as

`git push origin :serverfix`
but it may be easier to remember.

# Create and checkout to new branch:
`git checkout -b feature/profile-image-crop`

# Show last git commit
* `git show --summray`
this will show commit message
* `git show --stat`
this also show last git commit with change file list

# squashing
`squash` means combine couple of commits. Let you commit 5 commits to implement a feature but some of the commit
was only for `typo`. If you are thinking that all your code should be in one commit. Using  `squash` you can do it.

Let your feature branch name is 'foo-feature' and your base branch name is 'master'

```css
$ git log --oneline origin/master..foo-feature
73bbc09 add migratio
f33b240 do somthimg
f33b301 solve type mistake
```

Above command will show your all commits that you had made for implementing `foo-feature` feature.

`git rebase -i origin/master`

This will open your editor with these contents:

```css
73bbc09 add migratio
f33b240 do somthimg
f33b301 solve type mistake

# Rebase e54a9a9..73bbc09 onto e54a9a9
#
# Commands:
#  p, pick = use commit
#  r, reword = use commit, but edit the commit message
#  e, edit = use commit, but stop for amending
#  s, squash = use commit, but meld into previous commit
#  f, fixup = like "squash", but discard this commit's log message
#  x, exec = run command (the rest of the line) using shell
# ...
```

Change the pick to squash (or just s) (those commits that you want to squash, at-least leave top commit), save the file and exit. You'll then get another editor with a commit message to edit:

```css
# This is a combination of 3 commits.
# The first commit's message is:
```
Create your commit message and save. That's it.

# branch search
Let you have 40+ branche and most of the time you forget exact branch name. You can search your branc name in different ways

## Using grep
` git branch | grep foo`

above command will return those branches that contain `foo` word

## Using git wildcard search
 You can just use `git branch --list <pattern>` where `<pattern>` can contain wildcards:
`it branch --all --list *Theme*`

The `--all` option will include remote branches in the search.



{% if page.comments %}
<div id="disqus_thread"></div>
<script>
    /**
     *  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
     *  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables
     */
    /*
     var disqus_config = function () {
     this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
     this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
     };
     */
    (function() {  // DON'T EDIT BELOW THIS LINE
        var d = document, s = d.createElement('script');

        s.src = '//engr-hasanuzzaman-github-io.disqus.com/embed.js';

        s.setAttribute('data-timestamp', +new Date());
        (d.head || d.body).appendChild(s);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript" rel="nofollow">comments powered by Disqus.</a></noscript>
{% endif %}
