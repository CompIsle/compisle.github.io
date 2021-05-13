# Technical Induction - Level 3 Year 1

## Apps you will need on your local machine

+ Windows Pro. Ok, not absolutely essential thank goodness, as an upgrade from Windows Home is not cheap, but there are some things you will not be able to do with Home. If buying a new machine during your time at College, definitely go for Pro.

+ Office365. You get a free account courtesy of the college and it's a cloud app anyway, but note that you also get a licence and download link for the desktop versions of all the Office Apps if you need them. 

+ [Git](https://git-scm.com/). Do not confuse GitHub - an online/cloud store for Git repositories - with Git, the software for managing/creating/downloading repositories locally.

+ Visual Code. Do not confuse with Visual Studio (which you may also need but not until later). It can be downloaded [here](https://code.visualstudio.com/download).

	You will spend a lot of time in Visual Code. Learning to use it well will make a great deal of difference to how you get on. That, and learn to touch type, are the two most practical tips I can give you (there are many great online sites to learn touch typing).

+ Python. Get it from [here](http://python.org). You will want the latest stable version of Python 3 (definitely not 2) and there may be some advantages in going for a 32-bit version.

+ JS/TypeScript runtime. This will not be day one, so you can await your moment for making a choice here, but it is likely that at some point you will want the capability to develop server-side/local JavaScript or TpeScript applications. You will need a runtime. Your choices are [node](https://nodejs.org/en/) or [deno](https://deno.land/). Broadly speaking it is a choice between older, better supported and newer, still-evolving. 

+ More than one browser ... anything web-related that you develop will need to be tested on at least two browsers. Chromium and Edge both use the Chrome engine so are pretty similar (in the sense that there is no need to use both). Firefox would be the other obvious choice and is very solid for web development.

+ Microsoft Teams. Part of Office365 but also available as a desktop application which will give you greater capabilities. Install Teams on your phone too. It is our primary means of communication.

## Optional Local Packages

+ You should be keeping anything irreplaceable in the cloud anyway, but some means of backing up your local machine is very useful and could save hours of re-installing software (let along the tens of hours getting all your preferences and options back where you want them). I commend [AOMEI Backupper](https://www.aomeitech.com/aomei-backupper.html) to you. Useful enough that I went for the paid version ...

+ Bootstrap Studio. If you end up getting into web development this is a really useful package. As a student you can get a free licence via the [Github Student Pack](https://education.github.com/pack) along with lots of other goodies.

## Hardware

### Needed

+ Portable drive. 
	
	A USB 3.2 Gen 1 or better, bus-powered, hard drive. Capacity fairly immaterial. A device based on an SSD is preferrable to one based on a 2.5" HDD (more robust, faster) and the M2 SSD based types are also a lot smaller. Price bands are narrow. You won't get what you need for much less than £40 and you are up into the sexy end of the market at £100.

	You _can_ get away without one of these now that OneDrive + GitHub  can be used for all your files, but that might be annoyingly slow for collections of hundreds of small files (a common situation when writing software) and thousands of files is not unusual for JavaScript development (at which point annoying is semantically equivalent to impossible).
	
	The USB naming system is mind-boggling, see [here](https://www.theverge.com/circuitbreaker/2019/2/27/18243425/usb-3-2-standard-names-connectivity-cables-innovators-forum) if you do not know your USB 3.2 Gen 1 from your USB 3.2 Gen 2 x 2. Be wary of anything labelled USB 3.0 or 3.1, technically these names have not existed since 2017 and the manufacturer is either a) lazy, b) pedddling old-stock, or c) trying to mislead you.

+ Headphones/headset

	You will need a headset at home for use with voice calls in Teams (unles you have a webcam with mike set up)

	You will need to have headphones with you in College for accessing video resources/YouTube/tutorials etc. It will not be predictable when this wil occur so you will always need to have them with you. Probably a pair of bulky, expensive on-ear headphones are less appropriate than a cheap in-ear set that can be stuffed into a pocket.

+ Webcam

	We avoid video calls where possible as some people find them uncomfortable and there is rarely any absolute need. However, there may be occasions when video calls are needed and if you are involved with any other departments of the College (Maths, English, Skills Support, student rep, student governor, ...) you may find them using Zoom. 
	
	*With either headsets or web cams make sure that you understand the security implications and know how to disable them.*

### Optional

+ A Raspberry Pi of your very own would be cool. You can get them [here](https://thepihut.com/) (other vendors exist). Your needs for the course would be met by a Pi Zero (under £10) but the plus side of a Raspberry Pi 4 (on which you could spend up to £74 if you think you need 8GB of RAM - you probably don't btw) is that it will run a full desktop at decent-ish speeds (4GB would be just as good for that) which gives you a backup machine if your Windows box won't boot one day. And if not ... has dozens of uses, caching proxy for that bandwidth intensive game, NAS, web server, media server ...

## Accounts on Web Services you will need

+ Google

	We will be using 
	+ Google OAuth authentication to access other service
	+ Google Drawing as our default vector graphics package
	+ Google Drive/Sheets/Docs as an alternative to Microsoft especially when sharing/collaborating with people that may not have Office 365
	+ Google Cloud services (advanced, maybe not everyone, and you might prefer to use Microsoft Azure) for SQL databases, web servers, running public Docker containers, ...
	+ Google Scholar for research

	If you have an existing Google account you may, of course, use it. If you have to create a new one, I ask that you select a username such that it is obvious to me which student belongs to that account. Ie, 'David3278' helpful, 'therubberduck' less so.

	Even if you have an existing personal account it might be useful to create another for _professional_ purposes, don't forget that you can easily combine mailboxes so that e-mail/messages to either ends up in the same place.

	Finally note that you need **at all times** to have a current personal e-mail, to which you have access via your mobile phone, recorded in your college profile. Without this you will be unable to reset your password if you ever get locked out of your college account.

+ Office 365

	All students have an Office 365 account as part of their enrollment. You should aim to become aware of all the applications - which goes way beyond Office and Teams - that come with this.

	Finally not that this also includes the right to download the desktop versions of the Office suite on machines (3?) of your choice. Do bear in mind that these will revert to being unlicensed once you leave the College.

+ One Drive

	Your "My Documents" will be on your College OneDrive via which you have effectively unlimited cloud storage that is secure.
	
	Do not:
	
	+ Save anything unique on the C: drive of whichever machine you happen to be using ... it will not follow you around and may vanish without warning if the machine is re-imaged.   

	+ Use USB drives. They do (and will after some number of hours) fail without warning. Even use for moving file from home to college is poor technique as it throws the problem of verison management and remebering to upload back onto you. The correct approach is to use the cloud (OneDrive or GitHub).

	If you have a personal as well as a College OneDrive you need to make some decisions about how to manage it. Only one can be mirrored to a local folder at a time on each machine.

	What you can do though, is map the other OneDrive as a network disc so that it is accessible through a drive letter. Instructions are [https://www.laptopmag.com/uk/articles/map-onedrive-network-drive](https://www.laptopmag.com/uk/articles/map-onedrive-network-drive)
	here. 
	
	Useful for your home machine, less so in College as you cannot create new drive mappings.

	 

+ Teams

	Teams will be our (tutors-you) primary means of electronic communication, file-sharing, making video and audio calls, holding online meetings, collaboration. You will need/want to install Teams on your mobile phone as well as your home machine for maximum convenience. It can also be accessed using the web from the Office365 portal although not all features will work without the desktop/mobile app installation (e.g. notifications )

+ GitHub

	Git itself is a version control system primarily aimed at source code (and its documentation, etc). It can cope with binary objects but is intended for and provides best for text. 

	A collection of files under git control is called a repository and it is simple `git clone ....` to create a new and exactly equivalent copy of that repository.

	Git does a lot more than that, but that is the core.

	GitHub is a cloud service that provides storage for Git repositories .

	GitHub does a lot more than that, but that is the core.

	GitHub (now owned by Microsoft) offers both paid and free accounts. The most significant limitation of a free account is (usually) that you cannot create private repositories, only public ones (note that public repos are far more important in general - GitHub is the major mechanism for sharing and publishing repos). 

	When creating source code your expected form of submission will be to provide the URL of a GitHub repo from where your source code can be obtained.

	Note, however, that keeping *all* of your assignments in the form of GitHub repos is recommended: it provides, with no extra effort, versioning, backup, archive, the ability to roll back in time to earlier versions, the ability to access your work anywhere ... 

	As a student you will be able to create private repos even as a free user: once you notify your tutor of your GitHub username he will be able to add you to an organizational team. Source code provided to you (eg an assignment might be to extend or debug or add features to some existing code) will normally be provided as the url of a GitHub repo also. 

	Same comments as for Google: it is helpful if which student you are can be deduced from your GitHub username.

+ Repl.it

	Repl.it is a cloud-based IDE for developing source code in a huge variety of programming languages. It has the advantages of allowing you to program in (pretty much) any language (and a good number of frameworks) from anywhere you have network without the inconvenience of installing compilers, editors, IDEs, etc.

	Additionally, Repl.it allows for collaborative programming where any number of invitees can see (and if allowed edit) code being developed live. 

	Repl.it does a lot more than that, but that is the core...

	A free account will be satisfactory for students.  

+ CodePen

	Similar to Repl.it but focussed narrowly on front-end web technologies, HTML, CSS, JS. We may not have occasion to use this at all during the first year. 

## and _strongly_ recommended

+ LastPass or similar password manager

	I use LastPass. Other password managers exist. _Use one_. You will be creating a great number of accounts. Keeping track of dozens of different passwords is impossible. Using the same username and password across multiple sites is incredibly foolish. 


## Generic skills and technologies that need to be mastered, not related to any particular unit.

### Markdown
Markdown is used extensively throughout the course for creating documentation. Markdown is a lightweight markup language, it ultimately generates HTML but in comparison with HTML it is intended to be easier to edit and more-or-less human-readable without being rendered. It is also straightforward to convert Markdown into PDF.
Use Markdown for:
+ making notes 
+ creating submissions for assessment (should be submitted as PDF but original source maintained as Markdown)
+ creating technical documentation 

#### Creating/editing Markdown
Many applications have Markdown capability, however, special mention is needed for
+ Visual Code. Standard Markdown is built-in and Extended Markdown, maths, UML diagrams, etc can be easily added by extensions. Visual Code also provides the fastest route for converting Markdown to PDF.
 
 	Advantages: feature-rich, a lot of time will be in spent in Code anyway, can keep documentation and code 'connected', integration with GitHub. 
 
 	Disadvantages. Thought has to be given to where folders are kept (GitHub repos are probably best), no instant access from Android or iOS although Windows, Linux and OS-X are all supported.

+ GitHub itself - *.md files can be edited directly on GitHub 
+ StackEdit - a browser extension that provides a full-featured Markdown editor. 
	
	Advantages: supports a hierarchical document collection that can by synched with your choice of cloud services (DropBox, GutHub, Google Drive); more WYSIWYG than Code (and a cheat sheet!); accessible wherever you can get a browser. 
	
	Disadvantages: ?
+ SimpleNote - An app available for at least the Web,  Windows and Android. Very similar to StackEdit.

	Advantages: Clean, simple interface. Good on mobile too.

	Disadvantages: Not quite as full-featured as Stack Edit; synchs with its own web-app rather than public clouds, so possibly more thought needed on data security (although it is simple to import/export content for routine backup).
	
### Other text-oriented editors 
Sometimes the formatting capabilities of Markdown will not be sufficient to the task in which case we have these options
+ Word sources converted to PDF: use when hybrid text/data capabilities are needed, eg. if it is essential to embed a spreadsheet or when mail-merge is the objective; or when the format is part-graphical, e.g. to make extensive use of Word Art.
+ HTML + CSS: ultimate flexibility, more complexity. Can be rendered as a PDF or left as HTML/CSS. However, in this case it should either be reduced to single-file HTML (by embedding any CSS/images or possibly linking only via public URLs) or mounted on a server, eg Netlify or Git Sites. 
+ If sophisticated layout facilities are needed, e.g. multifold leaflets or newsletters then consider using a proper DTP package such as Scribus. Once again, render to PDF for electronic submission. 

### Software as a Service (SaaS)

Some apps that don't fit into other categories are mentioned here

#### 2D graphics

Unless we are rich, we will not have a subscription to PhotoShop.

Try these online alternatives

+ [Figma](https://www.figma.com/) or [Gravit](https://gravit.io/) for vector graphics/icons/UI design
+ [Pixlr](https://pixlr.com/) for bitmap graphics

If you need something more powerful than Pixlr, i) why are you not on a graphics course? ii) [GIMP](http://www.gimp.org), but this is a desktop application (a free one) you would have to download and install.

#### Data analysis/projection

If you just need a UI to front your data then [Glide](https://go.glideapps.com/) is worth a look it lets you turn any Google Sheet into an app. 

[Airtable](https://airtable.com/) has its most powerful features behind a paywall, but even the free version is pretty useful, it's a kind of spreadsheet database hybrid that allows cells to have complex content and cells/tables/rows/columsn to have relational links.

### 3D Graphics

3D graphics (modelling/texturing/rendering/animation) are both CPU and GPU heavy. If you need to do some serious modelling you wil probably have to bite the bullet and install [Blender](http://www.blender.org/), free, but large and complex. You will not be able to do anything much without tutorials (YouTube has you covered, but watch the version numbers, the UI changed pretty considerably recenly, anything for Blender <2.8 is probably of little help)

For more trivial modelling jobs, Paint 3D can be installed form the MS Store if it is not already on your machine.

## Checklist

### Installations (home machine). Installation includes checking it *works* btw

[ ] Visual Code

[ ] Python

[ ] Git

[ ] Teams (dekstop)

[ ] Office desktop (as required)

[ ] OneDrive desktop client (as required)

[ ] Second browser of your choosing

[ ] Password manager. Your choice. Also your choice as to online or local (on a USB key), but online is recommended (because it can work with your phone too). Do this before you start creating accounts

[ ] PDF viewer (if none, [Sumatra](https://www.sumatrapdfreader.org/free-pdf-reader.html) is a good (free) choice )

Note that you also need to be able to *use* these packages, so at least skimming some basic tutorials would be part of the task. 

### Installation (mobile)

[ ] Teams

[ ] Learn (optional - see Learn for instructions)

### Accounts to create (free versions only unless you wish to do otherwise)

[ ] GitHub

[ ] Google

[ ] Repl.it

[ ] CodePen

[ ] Airtable
