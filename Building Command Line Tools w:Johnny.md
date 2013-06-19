###Building Command Line Tools

####Why Command Line Apps

-Precise

-Usually Small

-Usually quicker to build than web apps

-Usually build with re-use in mind

####The Unix Philosophy

Building small precision tools that do one thing and does it well.

While it works in combination with other tools it works together with other smaller parts (programs), it works in concert with the rest of the system. 

####Maildis ( Johnny's github )

https://github.com/jboursiquot/maildis

Description:  Extract name, email, & url from Excel doc  (mail dispatcher)

Used PrinceXML

http://www.princexml.com

Convert HTML to PDF

--Problem: Maildis does not output HTML

####Producing HTML

(the log file had one line for each email processed )

The following command yields they desired HTML

    sed 
    
    # see is a stream editor
    
    man sed
    
    # the sed utility reads the specified files, or the standard input if no files are specified.
    # modifying the input as specified by a list of commands
    # the input is then written to the standard output
    
http://www.gnu.org/software/sed/manual/sed.html
    
________

    sed -e "s/ ^ / - / ' ~ /.maildis.log > .maildis.md && markup .maildis.md
    
_________

####Combine to Produce PDF

    sed -e "s/ ^ / - / ' ~ /.maildis.log > .maildis.md && markup .maildis.md && prince  .maildis.html - o .maildis.pdf
    
_______

####Where to go next!  

Unix Philosophy (wiki)

Doug Mcilroy: 

Mailcatcher

Your Objects, the Unix Way  (blog post)

 http://blog.codeclimate.com/blog/2012/11/28/your-objects-the-unix-way/
 
 
####Take Aways:

Think small and use functionality to build tools (string smaller solutions together to solve problems)

Decompose the problem - root cause - then apply smaller tools or solutions 

####Unix Philosophy - "Do it Simply"  