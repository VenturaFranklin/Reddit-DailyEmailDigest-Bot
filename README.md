# Reddit Daily Email Digest Bot

This project was forked off in order to send emails instead of posting to a subreddit.

This was created in order to eliminate the need for [IFTTT Reddit Digest](https://ifttt.com/applets/biJKbfTg-reddit-weekly-digest?term=reddit+digest)

**Reddit Daily Email Digest Bot** is a Python bot designed to simplify the process of aggregating and sharing top posts from your favorite subreddits. It fetches the top posts from specified subreddits, compiles them into a neatly formatted daily digest, and automatically emails the digest to an email

## Key Features

- Can create daily digest of top posts from multiple subreddits.
- Fetch top posts from multiple subreddits in the time frame you want.
- Compile the fetched posts into a digest with post details.
- Email the digest to a designated email using mailjet.


## Getting Started

### Prerequisites

You'll need to have the following installed on your system:

- Python 3.x

### Installation

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/VenturaFranklin/Reddit-DailyEmailDigest-Bot
   ```
2. Change the project directory

   ```bash
   cd reddit-dailydigest-bot
   ```

3. Install Dependencies
   ```bash
    pip install -r requirements.txt
   ```

### Configuration 
### Reddit API Credentials

Rename the `.env.example` file to `.env` and add your Reddit and Mailjet API credentials. 
 - See [PRAW setup instructions](https://praw.readthedocs.io/en/stable/getting_started/quick_start.html#)
 - See [Mailjet setup instructions](https://github.com/mailjet/mailjet-apiv3-python?tab=readme-ov-file#installation)


### Subreddits 
Modify the `SUBREDDITS` variable in `config.py` to specify the subreddits from which you want to fetch posts. Don't include r/ before the name of the subreddit.

```python
SUBREDDITS = ['science', 'technology', 'maths', 'physics']
```

### Usage
After configuring it properly simply run the bot script :

#### Daily Digest Script

```bash 
python main.py
```
The bot will fetch that day's top posts from the specified subreddits, compile them into a daily digest, and email it to the configured email.



### Auto-running the script for the daily digest

To make your Reddit Daily Digest Bot run automatically every 24 hours, you can use a scheduler like `cron` (on Unix-like systems) or Task Scheduler (on Windows). Here's how you can set up the automatic scheduling :

**Automate Script Execution Every 24 Hours**

1. **Linux/macOS (Using `cron`)**:

   - Open your terminal.
   - Open your crontab file for editing by running:

     ```bash
     crontab -e
     ```

   - Add the following line to schedule your script to run every 24 hours:

     ```bash
     0 0 * * * /usr/bin/python3 /path/to/your/reddit-dailydigest-bot/main.py
     ```

   - Save the file and exit.

2. **Windows (Using Task Scheduler)**:

   - Open the "Task Scheduler" application.
   - In the right-hand pane, click on "Create Basic Task...".
   - Follow the wizard to create a basic task, specifying the task name and description.
   - Choose "Daily" and set the recurrence to "1 days".
   - Specify the start date and time.
   - Choose "Start a program" and browse to the location of your Python executable (e.g., `C:\Python39\python.exe`).
   - In the "Add arguments" field, provide the full path to your `main.py` script (e.g., `C:\path\to\your\reddit-dailydigest-bot\main.py`).
   - Complete the wizard, review your settings, and click "Finish" to create the scheduled task.

**Ensure Proper Environment Setup**

Make sure that your Python environment and working directory are properly set within your script to avoid any issues when it runs as a scheduled task.

**Testing and Troubleshooting**

Before scheduling the script to run automatically, test it manually to ensure it works as expected. Check the logs or output to identify and fix any issues.

### Contributing

Contributions are welcome! If you'd like to contribute to this project, please open an issue or submit a pull request.
