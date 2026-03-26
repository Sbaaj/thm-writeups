# Writeups from my TryHackMe learning journey. 

**Path 1: Introduction To Researching.**

  ### Task: Answer Example Research Question
  	
  Q: A JPEG Image may contain something hidden inside it, but how to get it out?
  		  
    Try google-ing "hidden things inside images", This shows results for "Steganography".
  		
  A: **Steganography**, the art of hiding information in plain sight.
      
    For this example, we can use Steghide, a steganography program. It is able to hide data in images and audio files.
    
    The color respectively sample frequencies don't change making the embedding resistant against first-order statistical tests. 
  
  **Commands**
  
    - steghide ( command ) [ args ]
  
        - embed, --embed
          - -ef, --embedfile (Specify the file that will be embedded). 
          - -cf, --coverfile (Specify the cover file that will be used to embed the date).
          - -sf, --stegofile (Specify the name for the stego file that will be created).
          
        - extract --extract
          - -sf, --stegofile (Specify thestego file).
          - -xf, --extractfile (Create a file with the name filename and write the data that is embedded in the stego file to it).

    Given a file, summer.jpeg, we use `steghide extract -sf '/summer.bmp' --xf '/summersecrets.txt'` to extract data hidden in the JPG with Steghide. 

---

**Path 2: Google Dorking**

  ### Task 1: Learn About Crawlers 

  Q: What are crawlers, and how do they work?
  		  
    Q1. Name key term of what a "crawler" is used to do. 
    Q2. Name technique that "search Engines" use to retrieve information about websites.
    Q3. Name an example of types of contents that can be gathered from a website.
  		
  A: Automated programs (often called spiders), used to browse the internet for content that can be indexed to further enhance search engines.

    A1. Index, the actual database where all the collected resources explored by the "spiders" such as URLs and keywords are stored.
    A2. Crawling, it is the prccess the crawler does of visiting a website and reading its code, then storing its information. 
    A3. Keywords, in the figures discussed in task 1, we used they example of "keywords" such as apples, bananas, and pears. The crawler scrapes a URL for these keywords and associates the persistence of them to the Domain. So when a user searches for "pears", all the crawled websites containing that keyword will display the domain. 

  ### Task2: Search Engine Optimisation

  **Search Engine Optimisation (SEO)** is the practice of prioritising domains that are easier to index, improving its visibility by attracting more people to it when searching specific keywords.

  ---

**Path 3: Nmap**

  ### Task 1: Understanding Ports

  When a computer runs network services, it opens a "port" to recieve the connection, responsible for making multiple network requests. For example, when you are using a browser, watching a movie, and chatting online simultaneously, data packets are sent to your network connection (Wi-Fi) and single IP Address. However this can result into the data incoming to be tangeled, your computer wouldn't know if an incoming packet was a piece of a youtube video or characters in a chatting message. This is where "ports" handle these network services by assigning each one a different port number, sorting the packets that keep the applications from seeing each other's data.

  Every computer has 65,535 ports that are available, many being standard ports. There are **1,024** standard ports that are "well known" (0-1023), reserved for system services that ever computer agrees on.

  Some types of well known ports: 

    Port 443: HTTPS Webservice

    Port 80: HTTP Webservice

    Port 139: Windows NETBIOS

    Port 445: SMB (Server Message Block)

  For this example, we want to attack our victim with fake traffic, however we don't know which of these ports have an open server, so we use _Nmap_. 

  __Nmap__ connects to each port of the victim in turn. It shows which port is open, closed, or filtered. It is the tool of choice for establishing active connections to a target system inorder to gather detailed information about the user and their resources.

  **Commands**
  
    - nmap ( Scan type ) [ args ] { target specification } 
    
  Some Scan Types:
  
    -sS (TCP SYN scan)

    -sT (TCP Connect Scans)
      
    -sN (TCP Null scans)

    -sU (UDP scan)

    -O (Enable OS detection)
    
    -sV (Version Detection)

    -v (Increase Verbosity)

    -vv (Further Increase Verbosity) * by a level, so two levels

    -oA (Output scans in three major formats)

    -oN (Output scans in a normal format)

    -oG (Output scans in a grepable format)

  ### Task 2: TCP Connect Scans

  
  
    
  
 

  
    

    

  
