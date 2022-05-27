****************************************************************************************************************************************************************************
                                                                                FINAL
Challenge 1  Obedient Cat                                                                              
![snip1](https://user-images.githubusercontent.com/98431057/170601123-7f7d5f71-eb1d-4732-bf84-b3dbae732aed.PNG)
The challenge gave a file named flag. After downloading the file and checking the properties for the file type, the file type was file. I decided to just open the file in notepad and the flag was there.

Challenge 2 Rot13 Cryptography
![snip1](https://user-images.githubusercontent.com/98431057/170601942-bd2b3f15-5c92-4ab7-ae30-d02b6946df4c.PNG)
The rot13 is a simpler form of encryption. There are many online decryptors. I used rot13.com to decrypt and find the flag. It was as simple as copy/paste. The encrypted form was:cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_GYpXOHqX} The decrypted output is: picoCTF{next_time_I'll_try_2_rounds_of_rot13_TLcKBUdK}

Challenge 3 Python Wrangling
![first step mistake](https://user-images.githubusercontent.com/98431057/170602280-d3c5d57d-2e85-4983-9fe6-7f938f4f9a8a.PNG)
My first step was copy the code into an online compiler like replit.com. However, the program did not compile properly. It did allow me to enter the password into a pseudo terminal but it did not work.
![hint command used](https://user-images.githubusercontent.com/98431057/170602917-27db3e2e-9896-4a50-bf09-48431ba3aa15.PNG)
The first hint gave this command wget https://mercury.picoctf.net/static/1b247b1631eb377d9392bfa4871b2eb1/ende.py. When entered into the picoCTF online CLI it would reference the ende.py file. I tried opening flag.txt.en file in notepad but the flag is encrypted.However, from the site you can open flag.txt.en in a new browswer tab and copy the url https://mercury.picoctf.net/static/1b247b1631eb377d9392bfa4871b2eb1/flag.txt.en. When entering that url with 'wget' command. It will add the the flag file into the CLI. I verified which directory flag.txt.en was saved and tried running.
![second command for flag txt url](https://user-images.githubusercontent.com/98431057/170603199-cf235227-4255-46ad-9d00-9ad92ccee2eb.PNG)
Using the second hint man python I was able to view the manual to figure out how to get the flag. The command "python ende.py -d flag.txt.en" the flag -d means depcrypt. Once the command was entered I was prompted for the given password and the flag is given.
![final steps for flag](https://user-images.githubusercontent.com/98431057/170603334-bec84959-6776-478e-a757-42b0a022bf01.PNG)

Challenge 4 Wave a Flag
![snip1](https://user-images.githubusercontent.com/98431057/170603424-78a30552-657d-400f-93bc-fed351df6fc4.PNG)
I first downloaded the file. Which does not help. I tried opening it in notepad and the text was not useful. Going through the hints showed that the file will only run in CLI. I had to enter the command: wget https://mercury.picoctf.net/static/a00f554b16385d9970dae424f66ee1ab/warm. This would refernce the warm file into the shell. I verify that the warm file is in the shell. The next hint suggests to use chmod +x to the file. This modifies the permission to allow execution of the file.After enterying ./warm, it mentions use -h to find more info. Upon entering ./warm -h I got the flag.

Challenge 5 Codebook
Two files are given. I opened both links to download each file in a new broswer tab. I used the wget <url>. This added each file into the shell. I verified this using the ls command to make sure the files where in the same directory. From there i ran python code.py and retrieved the flag.
![firststep_addfiles2shell](https://user-images.githubusercontent.com/98431057/170603624-ed50b84f-a885-46aa-a342-306e657a9027.PNG)
![runpythonandfile_getflag](https://user-images.githubusercontent.com/98431057/170603657-a23c704b-bf79-4b6e-b8dc-ea1847409fa3.PNG)

Challenge 6 Nice Net Cat
I entered the command provided: nc mercury.picoctf.net 22902 into the shell. After that I got a series of numbers as the output. The hints indicate I should use ASCII to convert the numbers. The numbers are for crafting the flag. It was easier for me to do it by hand with an ASCII table from a programming book. But any ASCI table or script will work. The final number character 10 converts to ^J. This was not accepted by the text box as a valid flag. The format of previous flags gave me a hunch that it was a useless character. I tried entering the flag without ^J and it was correct. 
![firstcommandhint](https://user-images.githubusercontent.com/98431057/170603945-c2fe1f17-1a23-41fc-9bf8-fbbd5364085e.PNG)

Challenge 7 Forensics
First I had to save the cat.jpg file to the pico webshell. Second I had to install the exiftool. Once I stalled the exif tool I extracted the metadata. Within the exiftool directory I used ./exiftool t/images/cat.jpg. The License stands out and looks out of place. I suspect that its base64. I run an echo command with the license number and pipe it to base64. The last output displays the flag.
![catimage_metadata](https://user-images.githubusercontent.com/98431057/170604284-00fce413-908f-4179-a370-615e6798cf23.PNG)
![finalcommand_flagoutput](https://user-images.githubusercontent.com/98431057/170604317-27556307-e894-4e69-b74d-9b4667542743.PNG)

Challenge 8 Tab Tab Attack
First I had to save the cat.jpg file to the pico webshell. Second I had to install the exiftool. Once I stalled the exif tool I extracted the metadata. Within the exiftool directory I used ./exiftool t/images/cat.jpg. The License stands out and looks out of place. I suspect that its base64. I run an echo command with the license number and pipe it to base64. The last output displays the flag.
![snip1](https://user-images.githubusercontent.com/98431057/170604508-eb1501b6-9d36-4d56-8778-b5644fd76a23.PNG)

Challenge 9 Static
I downloaded the static file into the webshell. After using the cat static to see what kind of output, the flag was just there. I didn't need to use the seperate script provided.
![snip1](https://user-images.githubusercontent.com/98431057/170604600-e1380fa3-df2c-4030-aa57-6a0fdd249eaf.PNG)
![snip2](https://user-images.githubusercontent.com/98431057/170604619-d2ed3061-e64c-45ff-bfa8-a29f1d9e572c.PNG)

Challenge 10 Web Exploitation
The target website appears to only have 2 options. After looking at the page source you can see "head" as part of the title for pagesource. GET and POST appear as well. Indicating these are the main 2 options. The hint indicated a third option and its likely Head is the third. I tried: curl -I Head -i <url>. THe shell outputed the flag.
![head](https://user-images.githubusercontent.com/98431057/170604763-1b275a5c-b256-4f85-b7bf-e7d877a9ad49.PNG)
![snip1](https://user-images.githubusercontent.com/98431057/170604784-5822ab44-b7a2-4f00-b981-77abc219daa0.PNG)
****************************************************************************************************************************************************************************
Week 15 5/27/2022. Investigating Windows. This was a form of cyper forensics on a compromised machine. Had to find which users had admin priviliges and when were their last logins. Anything that seemed out of place. Scheduled task was created to clean system files to hide malicious activity. Discovering when escalation of privileges was done. Finding malicious file in system 32 directory that connected the host to an IP the attacker controlled.

Week 13 4/23/2022. The whole set of aircrack tools is something I will have to spend more time exploring. Learned about SSID's, BSSID's, and ESSID's. WPA-2 isn't perfect and still very vulnerable. Kali has an existing word list that we used to find the password from the .cap file.

Week 12 Lab 12 4/16/2022. This week in Tryhackme I deployed a vulnerable machine and used nmap to enumerate a machine for SMB shares. This was an interesting CTF because we were exploiting a network file system to root access to a Linux machine named "Kenobi." An interesting mistake towards the end of the lab was the section on Privilege escalation. If not done properly or changing to the wrong directory you would lose root access to the target machine.

Week 7 Lab 5 3-12-2022. The Cryptography saga continue with Keybase. I used the windows version since it seems that Keybase is no longer available for android. This was quite fun trading little encrypted files with my partner. I sent an encrypted .txt file to my partner which they decrypted. I also received an encrypted .txt file which I decrypted. I like how Keybase shows you the hash value during the encryption. I think I will build on this and see if John the ripper can decrypt the messages.

Week  6 Lab 4 3-5-2022. Cryptography is the name of the game this week. Had a chance to decrypt an RSA key. In my first few programming courses I tended to avoid using the modulo operator. I didn't know how important it was to cryptography. It was interesting to learn that assymetrical encryption is great but definitely the most inconvenient. That's why HTTPS uses symmetrical encryption.

Week 5 Lab 3 2-25-2022. This week we did mobile malware analysis. We used MobSF to analyze malware files, find hashes, id's. I was able to view the full source code of mobile malware. Virustotal.com provided depper analysis from different antivirus software. It was cool that you could just upload a file or a hash. I had never used "Get-FileHash" before. I may start finding more ways to use that command.

Week 4 lab 2-18-2022. This weeek we learned about various OSINT tools. Like viewdns.info and archive.org. These are great tools to track down websites that exist or may no longer exist. The information found can be used to dertermine if the website is legitimate or just used tricking search engine algorithms.

Week 3 Lab 2-11-2022: Reviewed different attack vectors such as social engineering, password cracking, and malware. Tried different simluation rooms like main in the middle showing how https and vpn can prevent a hacker or another entitiy from snooping in. 

Week 2 Lab:I identified different cybersecurity roles such as penetration tester and security analysts. Penetration testers are legally employed by organizations to find vulnerabilities. Security analysts are hired to detect threats before they are carried out.
