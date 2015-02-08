# Mac or Windows?  I choose neither.
While making my way through the first module of HIST 3907 I came across something that was going to provide me with a challenge.  The instructions for creating an open notebook were only for Windows and Mac users!  Now, I don't have anything against either operating system, but I prefer to do all of my work in Ubuntu for a number of reasons.  First of all, I do not own a Mac.  Secondly, and most importantly, for me, Windows is full of distractions and anytime I try to do some work while on Windows I find myself doing something completely unrelated for an extended period of time.  This often results in some late, stressful nights where I scramble to finish something which I should have finished days ago.  So one day I decided to log onto the other partition on my hard drive which housed Ubuntu and had been ignored for so long.  The results were amazing.  After logging on I found myself in an undisturbed environment with nothing to distract me.  There were no games, movies, or tv shows calling my name begging to be watched.  There was nothing except for the task which needed to be completed.

Since then I have always done my work on Ubuntu.  I find it much easier this way and that is why I have also chosen to do the work for this class on Ubuntu.  So when the first module called for the creation of an open notebook I navigated over to Google and searched for a linux substitute for Notational velocity.  What I found was an open source program called nvPY.  This program is a a simple clone of Notational Velocity which syncs to the online service Simplenote.  However, it takes a bit of setting up in order to get it working properly.

After a quick search, I found the Github account of nvPY's creator [here](https://github.com/cpbotha/nvpy).  In the README.rst file is everything I needed to know about setting up this program.  However, I did not initially want to sync my notes with a Simplenote account and I noticed that the notes were not saved as *.txt files, but rather a *.json file instead.  This made it difficult to easily share my notes on Github.  So before I fixed the problems I just mentioned, I created a file called '.nvpy.cfg' just as the readme file recommended.

After creating the .cfg file I searched again to find a way to save each individual note as a .txt file in the folder of my choosing.  After a while I found a blog article which showed me how to do it.  This blog can be found [here](http://mylinuxlife.com/installing-notational-velocity-and-its-cousin-nvpy/).  The instructions say to change the .nvpy.cfg file and add the following block.

    # cat .nvpy.cfg 
    [nvpy]
    notes_as_txt = 1
    txt_path = /your/path/here/
    simplenote_sync = 0
    
This worked like a charm.  I opened nvPY, I made notes and when I checked in the folder I specified, they were there as .txt files.  I was all done!  Right?  Wrong.  Now everytime I closed and re-opened nvPY, my notes were gone in the program, meaning that it was not syncing with the folder I had made to house the .txt files.

So after searching some more and coming up empty, I decided to try creating a Simplenote account at http://www.simplenote.com.  After creating my account, I navigated back to the [readme file for nvPY](https://github.com/cpbotha/nvpy) and I looked for the code I needed to sync my notes to Simplenote.  The code I found is below.

    sn_username = your_simplenote_username
    sn_password = your_simplenote_password
    
This code is simply added to the bottom of the .nvpy.cfg file which I created at the start.  There was one other thing I needed to do in order for the notes to sync properly and that was to remove one line from the initial creation of the .nvpy.cfg file.  The line which needed o be removed was     
    
    simplenote_sync = 0
    
Now everything worked just as I wanted.  Every note was saved as a .txt file in the folder I specified and when I opened nvPY it loaded my notes everytime.  The end result of the .nvpy.cfg file is below.

    [nvpy]
    notes_as_txt = 1
    txt_path = /your/path/here
    sn_username = Your_User_Name
    sn_password = Your_Password