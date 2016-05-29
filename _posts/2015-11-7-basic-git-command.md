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