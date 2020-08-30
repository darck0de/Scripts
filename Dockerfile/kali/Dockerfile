# My Kali Docker Setup

## Download this file and run below command from your current directory where this Dockerfile exists
## sudo docker build -t darck0de/kali:latest .

## Once completed run below command to get access to kali
##Usage: sudo docker run -it --name kali -h kali darck0de/kali

FROM kalilinux/kali:latest AS base
RUN apt-get update

FROM base AS essentials
RUN apt install git metasploit-framework sudo curl enum4linux gobuster nikto smbclient smbmap snmp sslscan python3-impacket nmap -y

FROM essentials AS big
RUN apt install seclists -y

FROM big AS autorecon
RUN sudo apt install python3-pip -y
RUN python3 -m pip install --user pipx
RUN python3 -m pipx ensurepath
RUN python3 -m pip install git+https://github.com/Tib3rius/AutoRecon.git
RUN sudo apt install nbtscan onesixtyone oscanner smtp-user-enum sipvicious tnscmd10g whatweb wkhtmltopdf -y
RUN apt-get -y autoremove && apt-get -y autoclean
