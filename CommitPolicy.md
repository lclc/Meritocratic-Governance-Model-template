**Commit Policy**
=================

These are the general rules for creating and pushing commits to any shared Open-Transactions repositories. None of these rules is set in stone, but you *will* be subject of public reprimand if you violate them without good reason.

 1. If you add new functions/classes:
    - Ensure everything is documented properly.
    - Discuss and verify the names of functions/classes with other OT developers (conduct API reviews).

 2. All code should follow the Coding Conventions [lclc link].

 4. Ensure your change compiles and works on all platforms. We will not allow your change to go in if it does not compile.

 5. Verify that there are no regressions in the unit tests.

 6. Write new unit tests for the bugs you fixed or functionality you added.

 7. Make your new/changed code follow the coding style [lclc URL].

 8. Produce commits which facilitate reviews and contribute to a useful history which can be read, searched, annotated and cherry-picked. In particular:
    - Make atomic commits. That means that each commit should contain
    exactly one self-contained change – do not mix unrelated changes, and
    do not create inconsistent states. Never “hide” unrelated fixes in
    bigger commits. Make coding style fixes only in exactly the lines
    which contain the functional changes, and comment fixes only when
    they relate to the change – the rest is for a separate commit.
    - Write descriptive commit messages. Make them self-contained, so
    people do not have to research the historical context to make sense
    of them. Conversely, do not put unnecessary trivia into them. Tell
    why you changed something unless it is completely self-evident; this
    is particularly important for reverts. Follow the summary +
    description message style and use footers to reference JIRA issues,
    reviewers, etc. and consider the generic Git commit message
    guidelines [http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html].
    - Commit often. Use git gui and git rebase -i extensively to get your
    unpublished history into shape. Note that pushing to your private
    clone does not count as publishing and is a perfectly valid way to
    solicit an early review or to make a backup of a work in progress.
    Further reading: Understanding the Git Workflow
    [https://sandofsky.com/blog/git-workflow.html]
    - Avoid unnecessary merges. Use git pull —rebase unless you have an
    unpushed “proper” merge.

 9. Do not commit anything you do not understand. “Somehow it suddenly works” is not acceptable. Reverting when a proper fix would be possible is admitting defeat. ;)

 10. Review your changes before you push to Gerrit. git log [—stat] [—summary] [-p] @{u}.. and gitk are your friends.

 11. Make sure you submit against the lowest applicable branch from which a release is still planned. Cherry-picks (“backports”) are frowned upon, while forward-merging to more recent branches happens “automatically” on a regular basis.

 12. Peer review is strongly encouraged. Do not approve your own changes. Discuss objections. If there is no candidate for a review yet, introduce somebody to the code.

 **Maintainer privilege:** A maintainer may approve his own change to the code he maintains if
  - at least one review (+1) from somebody else is present, and
  - nobody else who could approve (+2) the change can be produced within reasonable time

 13. Do not ignore/fight the Early Warning System. Justify each override.

 14. And most importantly: use your brain.




**Change Log**
----------

If the change is significant and affects many users, compatibility or is a noteworthy feature, you must add a ChangeLog tag.
* A [ChangeLog] entry can be multiple lines long and ends with an empty newline.
* If the Git repository contains multiple modules, use the module name to indicate the area of the change e.g. [Core].
* Optionally specify a class or subtopic [Core][Cheque]
* Other common tags are:
    * [Trade]
    * [Client]
    * [Important Behavior Changes]
    * [Platform Specific Changes]
    * [Windows]
    * [OS X]
    * [Linux]
* In summary the entry should look like this:

>  [ChangeLog][module][class/topic] description of the really important
> change that was just made (on several lines).


Content is available under Creative Commons Attribution-ShareAlike 2.5 Generic
[qt-project.org](http://qt-project.org)
