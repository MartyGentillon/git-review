# git-review

A distributed local code review tool for Git.

So, the other day, I was working on a small project with one other collaborator,
when we were discussing the contents of a text document.  Now, I had a number of
comments to make on this document, but realized that I was lacking a good tool
to do so:

  * I could use one of the many standard centralized code review tools, but, all
    of those are centralized services.  I would have had to set it up, and
    upload the file before I could make any comments.  This is far too much
    overhead for what should be such a simple task.  Moreover, once set up, the
    data is now stored in the tool's database, making interactions with other
    tools somewhat difficult.
  
  * Alternately, I could use Microsoft Word, a tool which has essentially taken
    over the publishing industry on account of its powerful change tracking and
    commenting features.  However, it is also an expensive proprietary product
    which places far too much emphasis on distracting details like formatting.
    Worse still, its monolithic fully-integrated design prevents easy extension
    and integration into other workflows; it is a cancer that, once adopted,
    extends to consume your entire workflow.  In short, it does not play well
    with others.  Worse, there is no guarantee of backward compatibility.  I
    have old word documents which I am not entirely sure that any tool can still
    read.

All of this lead me to ask: what would I want in my perfect review tool?

1) Technical simplicity — While good tooling is important, it must be possible
   to manage the manage all of the data with nothing more than a primitive text
   editor.  This kind of simplicity insures that other developers can write
   tools to interface with the data themselves.  It also ensures that comments
   will remain readable long into the future, as manually interpretable files
   are unlikely to ever suffer from unsupported lack of backward compatibility.
   Moreover, by building on such formats, this should be able to be extended to
   support other version control systems or even comments on files without
   version control.

2) Entirely local operation — It must be possible to start and update a review
   without a connection to the internet.  All of the relevant data should be
   stored on the local computer.  Of course, internet hosted services are a
   valuable interface, but they should not be the only option.

3) Binding to file history — All reviews should be stored with the version
   history of the files being reviewed.  This means in the version control
   system, or Git.

4) Distributed operation — It should be possible to have multiple people
   participate in the review without having to coordinate with each other.

5) Open data formats — It should be possible for anyone to write tools to
   support these reviews.  To support this, the tool should be focused on the
   data structures, rather than the interface.  Furthermore, to work on multiple
   workflows, the data structures should be open, able to support additional
   data.

6) Immutability — A code review, once published, should be part of the
   historical record of the project, and not subject to mutation, much like the
   history of the file itself.

## Related Tools

* [git-appraise](https://github.com/google/git-appraise) — Stores review content in git notes.  This does not meet the technical simplicity nor the open data formats requirements.
