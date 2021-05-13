# Workflow - How to create, manage, store, submit work

## This guide is primarily aimed at L3 students, but is good general guidance

This guide is mostly advisory, generally speaking we are less concerned with 'how' than with 'what'. Where things are **course requirements** they wil be in bold.

### Notes and Research

It is *highly recommended* that you create notes using Markdown (ie plain text with Markdown markup). Reasons:
+ Commonality with how you will have to work for web site/source code documentation
+ Being able to 'live' within either the browser or Visual Code and not have to duck out into other applications
+ Flexibility of rendering as either HTML (view on screen) or PDF (screen/print)
+ Ease of linking to other documents 
+ It has just enough functionality for notes (images, hyperlinks, formatting) without being over complex. It is very easily searchable (being just text).
+ directly editable within eg GitHub

What you are going to use to take notes is a matter of opinion. My narrow recommendation would be Visual Code but there are good arguments for StackEdit (I spend a lot of time in the browser) or SimpleNotes (I want a native mobile app too). Note that 'just text' (Markdown) is very portable so individual files can be moved freely between all of these.

Do note though, that incorporating images that are _local_ - not accessed through http as a URL but files - will only work well with Code. There are reasonably obvious workarounds for the others, but it is something to think about. (Matters because you may well need to add screenshots to your notes)

Where your notes live is going to be a function of convenience, security, and what application you are using.

+ Code users would almost certainly want to make use of Code's excellent Git integrations to keep their notes in a Git repository and synced with GitHub. Alternatively, keeping the folder structure on OneDrive and ignoring GitHub would be possible, but decide yourself whether this sacrifices useful features for illusory convenience).

+ StackEdit users will find sync built into StackEdit. Syncing is possible with Google Drive and GitHub (amongst others) though sadly OneDrive is not supported.

+ SimpleNotes has its own 'on server' sync feature, so registration via the web site is needed.

My final recommendation would be Code. StackEdit and SimpleNotes are both excellent for notes, but have weaknesses for assignments (eg. StackEdit will not let you render output as PDF on a free account) which means that at some point you will need to use Code anyway. There may be gains in using one tool for everything.

### Assignments

**Assignments will be submitted as PDFs and/or links to GitHub repos.** 

Exceptions may exist for specific units or assignments, for instance in the Digitial Graphics and Animations unit, your tutor will undoubtedly want other file formats used. Follow your tutor's instructions, do not deviate from the above without instructions. I can (and am quite likley to) configure Learn to accept only PDF by default.

There are two reasons for this: i) PDF is non-editable (well, mostly) and it is not appropriate that your work could be edited in any way by you, me, anyone after it has been submitted for assessment ii) PDF can be read by anyone on any operating system using free tools, unlike (e.g.) Word. 

PDFs can't be used for things that have to *do* something, projects, apps, web sites, so for those you will upload the url of a GitHub repo. These are editable, but all changes are tracked so there is still a robust audit trail. (btw GitHub repo is used broadly here, Gists count too)

#### Outline workflow for a documentation assignment

1. Create a private repo on GitHub in your organizational team area
2. Clone the repo locally
3. Create your document as Markdown marked text, possibly linking to other local resources (eg images)
4. Commit and sync your repo as the work progresses
5. Output as a PDF (this embeds local resources giving an independent single-file result). Proofread. Repeat as necessary.
6. **Upload the PDF to Learn**

#### Outline workflow for a project assignment

1. Create a private repo on GitHub in your organizational team area
2. Clone the repo locally
3. Create your source tree 
4. Commit and sync your repo as the work progresses
5. Test. Repeat as necessary.
6. Sync
6. **Upload the GitHub url to Learn**




