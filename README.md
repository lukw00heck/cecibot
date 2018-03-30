# cecibot

## Installation Instructions
1. Ensure that the following directories exist (if not, make them):

       ~/.cecibot/monitor
       ~/.cecibot/fetcher
       ~/.cecibot/email
       ~/.cecibot/telegram

2. Use [StevenBlack's hosts](https://github.com/StevenBlack/hosts) to block
   adware & malware:

       sudo wget https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts -O /etc/hosts
       sudo ifdown --exclude=lo -a && sudo ifup --exclude=lo -a

   * You should update your hosts file regularly (preferably every week, or at
     least once a month), using the same commands.

3. Install the latest version of Python 3:

       sudo add-apt-repository ppa:deadsnakes/ppa
       sudo apt-get update
       sudo apt-get install python3.6 python3.6-dev

4. Install `pip`:

       wget https://bootstrap.pypa.io/get-pip.py -O - | python3.6 - --user

5. Install *redis* using [*chris-lea*s PPA](https://launchpad.net/~chris-lea/+archive/ubuntu/redis-server):

       sudo add-apt-repository ppa:chris-lea/redis-server
       sudo apt-get update
       sudo apt-get install redis-server

### Backend

#### Fetcher
1. Install all the dependencies of the fetcher:

       python3.6 -m pip install --user pyppeteer redis requests

#### Monitor
1. Install all the dependencies of the monitor:

       python3.6 -m pip install --user redis

### Frontends

#### E-Mail
1. Install all the dependencies of the E-Mail frontend:

       python3.6 -m pip install --user flask redis

#### Telegram
1. Install all the dependencies of the Telegram frontend:

       python3.6 -m pip install --user python-telegram-bot redis

### The Web
1. Install nginx:

       sudo apt install nginx

2. Install Certbot for Let's Encrypt and follow all of the instructions on their
   website to get an HTTPS certificate for both `cecibot.com` and
   `www.cecibot.com` with HTTP -> HTTPS redirection enabled for both:

   https://certbot.eff.org/lets-encrypt/ubuntuxenial-nginx
