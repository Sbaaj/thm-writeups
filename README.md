A collection of writeups from my TryHackMe learning journey. 

Path 1: Introduction To Researching. 

  - Task 2, EXAMPLE RESEARCH QUESTION
  	
  	- JPEG Image may contain something hidden inside it, but how to get it out?
  		- Try google-ing "hidden things inside images".
  		
  	- By using Steganography, the art of hiding information in plain sight. 
  		- For this example, we can use Steghide, a steganography program. It is able to hide data in images and audio files. 
  		- The color respectively sample frequencies don't change making the embedding resistant against first-order statistical tests. 
  		- steghide ( command ) [ args ]
  			- Commands I looked at:
  				- embed, --embed
  					- -ef, --embedfile (Specify the file that will be embedded). 
  					- -cf, --coverfile (Specify the cover file that will be used to embed the date).
  					- -sf, --stegofile (Specify the name for the stego file that will be created).
  				- extract --extract
  					- -sf, --stegofile (Specify thestego file).
  					- -xf, --extractfile (Create a file with the name filename and write the data that is embedded in the stego file to it).
