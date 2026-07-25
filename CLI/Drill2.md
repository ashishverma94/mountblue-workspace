# Drill 2 Problems

##  **Pipes**
### 1) Download the contents of "Harry Potter and the Goblet of fire" using the command line

### Command
``` 
wget -O "harry.txt" "https://raw.githubusercontent.com/bobdeng/owlreader/master/ERead/assets/books/Harry%20Potter%20and%20the%20Goblet%20of%20Fire.txt" 
```

### Explanation
- syntax is : wget -O [filename] [url]
- <i>wget</i> is used for downloading the content from web 
- -O is used to give the filname in which content is saved
---

### 2) Print the first three lines in the book

### Command
``` 
head -n 3 harry.txt
```

### Explanation
- head is used to display the top part of the file
- -n is used to give the number of lines to display
- -3 means number of lines 
---

### 3) Print the last 10 lines in the book

### Command
``` 
tail -n 10 harry.txt
```

### Explanation
- tail is used to display the last part of the file
- -n is used to give the number of lines to display
- -10 means number of lines 
---

### 4) How many times do the following words occur in the book?
    Harry
    Ron
    Hermione
    Dumbledore

### Command
``` 
grep -oE 'Harry|Ron|Hermione|Dumbledore' harry.txt | sort | uniq -c
```

### Explanation
- grep -o print each match in the file
- -i is used to ignore case of word ( optional ) 
- -E enable multiple patter just like regex for matching
- sort is used to group words
- uniq -c is used for counting occurences
---


### 5) Print lines from 100 through 200 in the book

### Command
``` 
sed -n '100,200p' harry.txt 
```

### Explanation
- sed is a stream editor used to process text
- -n suppresses the printing of the line from start
- 100,200p means print the selected lines
---

### 6) How many unique words are present in the book?

### Command
``` 
tr ' ' '\n' < harry.txt | sort | uniq | wc -l
```

### Explanation
- tr ' ' '\n' < harry.txt ( this part convert spaces into new line put each word in new line of harry.txt file)
- sort is used to sort the list so that uniq can work ( uniq removes adjacent duplicates )
- wc -l count the number of lines.
---

## **Processes, ports**

### 1) List your browser's process ids (pid) and parent process ids (ppid)

### Command
``` 
ps -C firefox -o pid,ppid
```

### Explanation
- ps displays info about running processes
- -C is used to select process by their command name
- -o gives the output format means pid prints first than ppid 
---

### 2) List your browser's process ids (pid) and parent process ids (ppid)

### Command
``` 
pkill firefox
```

### Explanation
- pikll is used to stop the process
- you can also stop by writing the firefox pid to kill the process.
---

### 3) List the top 3 processes by CPU usage.

### Command
``` 
ps aux --sort=-%cpu | head -n 4
```

### Explanation
- `list aux` print all the running processes
- `--sort=-%cpu` is used to sort the process based on the decreasing cpu usage
- `|` operator is used to pass the output of previous command to next command 
- `head -n 4` used to show the top 3 processes
---

### 4) List the top 3 processes by memory usage.

### Command
``` 
ps aux --sort=-%mem | head -n 4
```

### Explanation
- `list aux` print all the running processes
- `--sort=-%mem` is used to sort the process based on the decreasing memory usage
- `|` operator is used to pass the output of previous command to next command 
- `head -n 4` used to show the top 3 processes
---

### 5) Start a Python HTTP server on port 8000

### Command
``` 
python3 -m http.server 8000
```

### Explanation
- `python3` is used to run the server of python on particular port
- `--directory /your/path` is used in last to run server in specific directory ( optional )
---

### 6) Open another tab. Stop the process you started in the previous step

### Command
``` 
lsof -i:800
kill 1234
```

### Explanation
- `lsof` is used to list open files
- `-i` shows network files instead of regular files
- `:8000` this shows only process running on port 8000
- now copy the pid and then kill the process
---

### 7) Start a Python HTTP server on port 90

### Command
``` 
python3 -m http.server 90
```

### Explanation
- permission denied, ports from 0-1023 are previleged ports
---

### 8) Display all active connections and the corresponding TCP / UDP ports.

### Command
``` 
ss -tu -a
```

### Explanation
- `ss` is used to display all network connections
- `-t` for all tcp connections
- `-u` for all udp connections
- `-a` shows all sockets
- ---

### 9) Find the pid of the process that is listening on port 5432

### Command
``` 
lsof -i:5432
```

### Explanation
- no process is running on this port
- ---

##  **Managing software**

### 1) Install htop, vim and nginx

### Command
``` 
sudo apt install -y htop vim nginx
```

### Explanation
- `sudo` runs the command with admin privileges
- `apt` is ubuntu package manager use to install, remove and manage softwares
- `install` tells the apt to install the specified packages
- `-y` automatically answer yes to confirmation prompts.
- ---

### 2) Uninstall nginx

### Command
``` 
sudo apt remove nginx
```

### Explanation
- `sudo` runs the command with admin privileges
- `apt` is ubuntu package manager use to install, remove and manage softwares
- `remove` removes the specified packages
- ---

##  **Misc**
### 1) What's your local IP address?

### Command
``` 
hostname -I
```

### Explanation
- `hostname` this command displays the hostname and its related network information
- `-I` is used to display only ip address
- we can also use -f and -s to view the full hostname and short hostname.
- ---

### 2) Find the IP address of google.com

### Command
``` 
nslookup google.com
```

### Explanation
- `nslookup` this command is used to query DNS server and find ip address or DNS information of domain name
- ---

### 3) How to check if Internet is working using CLI?

### Command
``` 
nslookup google.com
```

### Explanation
- use this command if ip address is coming means internet is working
- you can also use other commands like `ping google.com` or `curl -I https://google.com`
- ---

### 4) Where is the node command located? What about code?

### Command
``` 
whereis node
whereis code
```

### Explanation
- this command gives the path of node
- ---


