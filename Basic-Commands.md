                         BASIC COMMANDS (linux)   
                         
1) pwd :-  present working directory shows the current directory folder or location we are on .
      for example suppose we logged from root .. now terminal → pwd .   [output = /root] .
      /root = home location .
      
2) ls :- lists of folders/directories ..
          suppose we are on home location i.e file explorer → computer → desktop documents pictures videos downloads local(C) .
          terminal → ls [output =  desktop documents pictures videos downloads local(C)]
          ls is the main command .

3) info :- provides information ..
              suppose we want to know the information of certain command like ls ..
              terminal → info ls [output = ls command information i.e meaning , features , etc ]
              terminal → ls [output = all information regarding commands and some basic commands].

4) man :- manual used for how to use it ..
               suppose we want to know that how to use (ls) then 
               terminal → man ls [output = how to use ls]   

5) ls --help :- -- help shows all (-) commands and their work .

6) ls -l :- this shows all the lists of document and directories in long format like ..
              -rw-r--r-1  root  root  393(k)  july 30 15:28 desktop 
              -rw-r--r-2  root  root  104(k)  july 30 15:30 documents

7) ls -a :- used to hidden files .
               In linux if we used (.) at the time of creating files then it becomes hidden .
               like .cache , .java , .profile , etc .
               
    we can use both at at time like .. ls -a -l  (or)  ls -al
    This will show all the hidden files in long format .                                                                       
                
8) ls -h :- human readable ..
                we saw in ls -l that files being shown in k format like 10k 393k etc .
                terminal → ls -a -l -h   or   ls -alh [output = -rw-r--r-1  root  root  30 mb/3000 kb  july 30 15:28 desktop]
                
9) ls -R :- recursive ..
                recursive means the whole data inside the folder . It will show the whole data inside and inside the particular folder .
                like /downloads /desktop /movies baaghi vampire diaries /pictures drag.jpg corf.png /documents /music etc .
                now movies and pictures shows files inside them .
                
10) ls -r :- reverse ..
                it will show the reverse data .. like command = ls -r
                desktop documents pictures videos downloads local©   to   local© downloads .... desktop  

11) cd :- change directory ..
              to enter inside a folder or file example our current directory is /root .
              command = ls [output = /desktop /downloads /documents etc .{/root}
              cd downloads = we will go inside downloads
              if whereever we are , we command = cd then it will back to the main directory we logged in i.e /root . 
              
12) cd .. :- change directory return one folder .
                 command = ls [output = /desktop /downloads /documents etc .{/root}
                 cd downloads = we will go inside downloads .
                 cd .. = we will again back to /root .
                 
13) mkdir foldername :- make directory foldername.
                                    command = mkdir foldername
                                    it will create a folder .
                                    we can create folder from a different location as well like suppose our pwd is root/downloads
                                    but we have to create folder anywhere else .then command = mkdir desktop/f1 .
                                    now f1 folder will be created .
                                    
14) clear :- to clear command screen .

15) / :- 1st folder i.e root , log ,bin ,etc ,usr .
           command = /var /root /log , etc .
           we have to go inside var so we have to use /log/var .
           
16) touch :- to create a blank file .
                  command = touch 1.txt , 2.txt (filename) .
                  
17) cat :- to see the contain inside file .
              command = cat 1.txt .(empty file currently)
             
18) cat > filename :- to place contain inside a file .
                              ctrl + c = save .
                              
19) rmdir :- to delete a directory
                 command = rmdir foldername 
                 it should be empty .
                 it will not delete the folder which has another file or folder inside .
                 
20) rm :- to delete a file or to delete a folder has contain inside .
              command :- rm filename .
              command :- rm foldername (it doesnt allow)
              then command = rm -rf (recursive and forcefully) foldername .
              it will anyhow delete the folder .
              
21) mkdir -p :- to create more folders inside a single folder recursive .
                      command :- mkdir -p krish/f1/f2/f3 .
                      
22) cp :- copy files  
             cp srcfile  dstfolder
             cp krish/f1/s1/1.txt    downloads/   files copied to dowloads
             cp krish/f1/s1/1.txt   krish/f1/s2/2.txt     documents/    1.txt and 2.txt copied to documents
            
23) -v :- verbose
              cp -v  krish/f1/s1/1.txt    downloads/    shows the list of copied file
              
24) -f :- forcefully
            rm -f krish/f1   forcely delete f1 folder
            
25) * :- wildcard
          cp krish/f1/s*   dstfolder   copy all files starting from s
          cp krish/f2/*.log              copy all files ending with .log
          
now suppose we have a folder krish ... meant files and folders inside it , when we copy krish folder to any other folder with cp command then it will occur as an error bcoz
cp only copies files not folders and krish has folders and files both , now to copy folder as well 
26) cp -r :- recursive 
                we want to target the subfolders as well .
                command = krish/*   .  {all files and folders inside krish to .(dot) ..dot represents pwd / current location}
                
warning :- rm -rf foldername is used to delete files recursive and forcefully . 
                but if we use rm -rf /   or   cd / then rm -rf *   then the whole operating system will get deleted bcoz all things start with / .            
                
27) mv :- move or rename files and folders 
              move is same as cut paste .
              now suppose we are inside krish/f1/s1
              command = mv root/downloads/1.txt .(. represents current location) .
              command = mv root/documents/file.txt krish/f1/s2 .
              now the file get cut from root/documents/ and now paste on krish/f1/s2
              
              now rename the file or folder
              command = cd krish/f1/s2/
              command = mv 1.txt 2.txt
              name changed to 2.txt
              
              To change the folder name 
              command = mv -v krish/ krrish [-v for verbose]
              
now if want to go inside any subfolder then we have to write the location like krish/f1/s1 again and again 
we could create a link direct to s1 folder .
link are of two types 1)soft 2)hard .
28) ln -s = link soft .
            command = ln -s[soft]    krish/f1/s1/1.txt    my_slink[name of link]
            now if go to 1.txt and cat 1.txt   or   cat my_slink
            the result will be same .
            it creates a commpressed file of the shorter length .
            changes occur in the main will unlink the soft link .
            
29) ln = hard link 
            by default it creates hard link ..
            hard is the mirror file of actual file lenght lik if the file lenght is 32mb then the hard will be same as 32mb .
            if any changes occur in the main file . changes occur in hard link as well.
            
30) less = command used to see the file content that can be displayed on the defualt screeen.
               like CUI doesnt have mouse accessibility so the file content could be too long .
               to view it on the actual screen we use less.
               command = less filename   or   filename | less .[arrow button is used to go up down left right]
               
31) more = same as less command but only use upper arrow key and down arroy key .

32) date = to know the date .
      date “+%m” = month
      date “+%d” = day
      date “+%y” = year
      date “+%d-+%m-+%y” = 22-8-2024     

33) id = to know about user uid gid and groups .

34) whoami = from which user we are logged in .

35) who = from which user we are logged in , how many remote connection through this .

36) who -a = detailed information of whoami with last login .

37) w = detailed information of whoami with last login with last commands generated .  

38) tty = terminal type .
             tty is the original terminator ...
             while when we use graphic then it provides pts .
             at the time of ssh connection it provides pts .
             
39) hostname = tells about current hostname .

40) hostname -a = tells about all hostname if was generated .

41) hostname -i = local host of the current user .

42) hostname -I = ip address v4 .

43) ifconfig = details of ip and interfaces(ip subnet netmask wordcast addresses).
      ifconfig -a = hidden interfaces
                    
44) uname = to check we are using linux or not .

45) uname -a = which linux we are using and about kernel .

46) cat /etc/os-release = to check which os version we are working on .

47) lscpu = to check cpu details .

48) lsusb = to check the devices connected through usb .

49) lspci = if something is on the pci slot .
                Developed by Intel Corporation, the Peripheral Component Interconnect standard (PCI) is an industry-standard, high-speed bus found in nearly all desktop
                 computers. PCI slots allow you to install a wide variety of expansion cards including: Graphics or Video cards.
                 
50) lsblk = all disk details and separation .
               like ssd 512 gb and distribution in different drives .
               
51) cal = calender
             command = cal year (cal 2020) will load the calender of 2020 .               
               
51) free -h = device memory and swap details .                                            

52) route -n = gateway .

53) cat etc/resolv.conf = DNS nameserver .

54) history = shows all commands that we had run .

55) uptime = the duration of time our pc is switched on .

56) exit and logout = to exit the current connection (root or armour etc) .

57) shutdown = to shut the server 
                       only root user can use shutdown 
                       a pop up will get shown to users that the server is going to get shut on the particular duration .
    
    shutdown -c = cancel ( if we want to cancel the shutdown within the given time) .
    shutdown -P = proper shutdown .
    shutdown -h = halt shutdown ( without any warning it get shut like we are plugging out , no services will be shown at the of screen off ) . risky
    shutdown -P now = shutdown without any notification it get closed immediately .
    poweroff = poweroff .
    init 0 = poweroff .
    init 6 = restart .
    shutdown -r = restart .                       



                                                        thankyou for watching                                
            
                                          
                          
                                                                                                                         
                                                                                                                                                                                                                    
                
                                     
