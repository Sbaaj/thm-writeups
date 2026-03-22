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

