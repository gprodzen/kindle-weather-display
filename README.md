# kindle-weather-display
Server and client software to generate an automated weather report on a Kindle.

Based on: https://mpetroff.net/2012/09/kindle-weather-display/, https://github.com/mpetroff/kindle-weather-display, https://www.youtube.com/watch?v=Oel08SDFyIY, and  https://github.com/yoonsikp/weather-display

Create key pair on AWS, store private key on development computer
Create an Amazon Linux instance on AWS
Set permissions of instnace to allow HTTP connections

Use Putty to SSH into server

Upload the server files using pscp e.g. pscp -i "C:/users/gprod/Downloads/kindlekey.ppk" -P 22 "C:/users/gprod/Desktop/server/weather-script.py" ec2-user@ec2-3-84-117-251.compute-1.amazonaws.com:/home/ec2-user/

Needed to fix formatting of .sh file using vi per https://askubuntu.com/questions/304999/not-able-to-execute-a-sh-file-bin-bashm-bad-interpreter

Installed rsvg-convert https://installati.one/centos/7/librsvg2-tools/

Installed pngcrush https://installati.one/centos/7/pngcrush/

Install web server via https://medium.com/@KerrySheldon/ec2-exercise-1-1-host-a-static-webpage-9732b91c78ef

Set up cron job to call script periodically

Navigate to http://3.84.117.251/weather-script-output.png from browser

Ran shell script https://www.cyberciti.biz/faq/run-execute-sh-shell-script/

Added to crontab */1 * * * * /home/ec2-user/weather-script.sh >> /home/ec2-user/crontablog.log 2>&1

Needed to install python-dateutil using pip
