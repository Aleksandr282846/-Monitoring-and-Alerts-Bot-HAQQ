# -Monitoring-and-Alerts-Bot-HAQQ
PANIC monitoring and notification system


PANIC is a open source code monitoring and alerting system for a node based on Cosmos-SDK, Substrate and Chainlink from Simply VC. The tool was created with users in mind and a lot of features such as quick send phone calls, Web-UI installation, and Telegram/Slack alerts.


# Install git
sudo apt install git

# Check version
git --version

# Install docker and docker-compose
curl -sSL https://get.docker.com/ | sh
sudo apt install docker-compose -y

# Check
docker --version
docker-compose --version

# Clone repo and change directory
git clone https://github.com/SimplyVC/panic
cd panic

# In catalog panic change parameters in file .env

INSTALLER_USERNAME: user

INSTALLER_PASSWORD: password

UI_ACCESS_IP: IP address host where PANIC is installed

# Run Panic

docker-compose up -d --build

# If the build fails, remove the docker images with the following command, fix the cause of the failure, and start the build again:

docker-compose kill
docker system prune -a --volumes
docker-compose up -d --build

# Setting up Telegram notifications

To create a Telegram bot, add @BotFather to Telegram, press Start, and follow these steps:

Send the /newbot command and specify the requested data, including the bot name and username

Write and save the API token, which looks like: 111111: AAA-AAA111111-aaaaa11111

Follow the link t.me/<username> to access the created bot and click Start.

Follow the link api.telegram.org/bot<token>/getUpdates, replacing <token> with the received bot token. A list of bot activities opens, including messages sent to it

There must be at least one message in the list, triggered by pressing the Start button. If not, send the /start command to the bot. Fix the "id" value in the "chat" section

This completes the creation of the bot, to create another bot, repeat the above steps again

# As a result, we should get:

Telegram account
Telegram bot
API token Telegram bot
Chat ID (chat ID)

# Configuring monitoring and alerts
Monitoring of notification nodes and channels is configured at https://{UI_ACCESS_IP}:8000. For authorization, we use INSTALLER_USERNAME and INSTALLER_PASSWORD, which we specified in the .env file.

After authorization, the monitoring wizard starts. All the necessary actions are intuitive and commented in detail. This manual can be used for other cosmos networks, but specifically in this case it was written to complete the task in HAQQ

Finally you need to change in app.toml API Configuration Section, string 114, you have to enable=False to enable=True, then save app.toml file and restart node
Thats ALL!!!1
