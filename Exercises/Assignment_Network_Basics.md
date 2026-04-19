# Assignment 1

Complete the exercises in this assignment.
Hand in a protocol documenting your steps while solving the exercises. On top of the protocol you must include:

 - Your name
 - Your student identification number (The one starting with cc)
 - Date you did the exercises on

Please hand in the protocol as a PDF including clearly labeled sections for each exercise.

## Exercise A (Current IP Address Configuration)

Find out

 - IP Address of your current device
 - Subnet mask of the network you are in
 - IP Address of the current Default Gateway

## Exercise B (ICMP)

Ping the Google open DNS resolver [8.8.8.8] while capturing packages on you network card using Wireshark. Find the ICMP echo request and response and capture a screenshot of a request and response that are connected. (Tip: use the Wireshark filter to filter for `icmp` to find your packets)

## Exercise C (Capturing a three-way handshake)

Find out the IP address of ustp.at (Tip: use `nslookup ustp.at` command)!

Use a web browser to reach the ustp.at webpage and while capturing packages. Find the TCP three-way handshake between your computer and the USTP server (Tip: Use the filter to filter for the IP address). Capture a screenshot that clearly shows the three-way handshake.

## Exercise D (TCP with netcat)

Find another person to work with and determine their IP address!

Start Wireshark to record packages on your network card.
Depending on your operating system use `nc` (Linux, macOS) or `ncat` (Windows) to open a server and listen on port 4444.
Have the other person connect to your IP address using `nc` or `ncat` to send a message to you. Grab a screenshot of the Package containing the sent message in which you highlight the data part.

## Bonus Exercise (ncat chat)

Find a person that has ncat installed.
Use Wireshark to capture traffic.
Start an unencrypted chat server using `ncat --chat -l -p 8888`.
On the other computers connect to the chat server using `nc` or `ncat`.
Use the group chat and inspect the traffic in Wireshark. How does is look like?