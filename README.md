# Shell Finder

---

## Description

**Shell Finder** is a security tool designed to identify **malicious shells** on websites. It works by scanning a list of URLs provided by the user and checking for the presence of known shell files in common web directories. The tool sends HTTP requests to detect these files, returning an HTTP 200 status code if the shell is present. The results can either be saved to a file or sent directly to Telegram if configured.

The tool offers a simple command-line interface and allows the user to choose between a predefined list of shells or a custom file for the search.

## Features

- **Fast Shell Scanning**: Searches for malicious shells in common web directories.
- **Flexible Input Options**: Provide URLs manually or via a file. You can also use the default or a custom list of shells.
- **Telegram Support**: Automatically sends results to Telegram if a bot token and chat ID are provided.
- **Multithreaded Execution**: Speeds up execution by using threads to make HTTP requests simultaneously.
- **Proxy Support**: Allows using proxies to hide your IP during shell search.

## Requirements

- **Python 3.x**: The tool is compatible with Python 3.6 and later versions.
- **Python Libraries**: `requests`, `time`, `os`, `re`, `concurrent.futures` are required.

```bash
pip install requests
```

## Installation

Clone the repository and navigate to the directory:

```bash
git clone https://github.com/HackfutSec/Shell-Finder.git
cd Shell-Finder
```

## Usage

1. **Run the Tool**:

   Simply run the Python script to start the process:

   ```bash
   python3 shell_finder.py
   ```

2. **Banner Display**:
   Upon starting the tool, a banner will be displayed with author information and license details.

3. **Provide a List of Shells**:
   You will be prompted to choose between two options:
   - Use the default list of known shells.
   - Provide a file containing shell paths, one per line.

4. **Provide a List of Websites to Scan**:
   You will be asked to:
   - Enter URLs manually.
   - Load a file containing a list of URLs.

5. **Option to Send Results via Telegram**:
   The tool will ask if you want to send the results via Telegram. If you choose **yes**, you will need to enter a **Telegram bot token** and a **chat ID**. A message with the list of found shells will be sent to the specified chat.

6. **Results**:
   The scan results will be displayed in real-time on the console, along with the HTTP status code for each request. If a shell is found, it will be saved in a file called `found.txt` in the current directory.

7. **Results File**:
   The shells found during the scan are saved in `found.txt` in the current directory.

---

## Example Execution

```bash
[+] Choose how to provide the websites for shell search:

1. Enter a list of URLs manually (separated by new lines).
2. Provide a file containing URLs (one per line).
Your choice (1 or 2): 1
[+] Enter the URLs (one per line). Type 'done' when you are finished.

[+] Enter URL: http://example.com
[+] Enter URL: http://anotherexample.com
[+] Enter URL: done

[+] Choose how to provide the shell list:
1. Use the default list of shells.
2. Provide a file containing shells (one per line).
Your choice (1 or 2): 1
[+] Scanning http://example.com for shells...
[+] Shell found: http://example.com/wp-admin/js/widgets/about.php [Code: 200]

[+] Shell found: http://anotherexample.com/wp-content/themes/aahana/json.php [Code: 200]

[+] Found shells saved in: /home/user/Shell-Finder/found.txt

[+] Press enter to exit...
```

---

## Sending Results via Telegram

If you wish to receive scan results via Telegram, the tool will prompt you to provide the following information:

- **Bot Token**: You can obtain a token by creating a bot through [BotFather](https://core.telegram.org/bots#botfather).
- **Chat ID**: This is your chat identifier. You can obtain it by sending a message to your bot and using the Telegram API's `getUpdates` method.

Example command to send a message via the Telegram API:

```bash
https://api.telegram.org/bot<your-bot-token>/sendMessage?chat_id=<your-chat-id>&text=<your-message>
```

---

## Advanced Features

- **Proxy Usage**: If proxies are configured, the tool will attempt to use them for the HTTP requests. If no proxy is provided, the tool will attempt a direct connection.
- **Request Delay**: A delay of 1 second is added between each request to avoid being blocked by the websites.
- **Error Handling**: The tool handles various types of HTTP errors, including timeouts (`Timeout`), forbidden access (`403`), and general connection errors.

---

## Security and Responsibility

**Shell Finder** is a powerful tool and should be used responsibly. This script should only be used for legitimate security testing on websites for which you have explicit permission to analyze. The author is not responsible for any malicious use of this tool.

---

## Contributors

- **Hackfut** (Lead Author)  
  Contact me via [Telegram](https://t.me/H4ckfutSec) or on [GitHub](https://github.com/HackfutSec).

---

## License

**MIT License**  
You can use, modify, and distribute this software under the terms of the MIT license. See the `LICENSE` file for more details.

---

## Support

If you encounter any issues with the tool, you can open an **issue** on the GitHub repository or contact me directly via [Telegram](https://t.me/H4ckfutSec).

---

## Disclaimer

Shell Finder should only be used for educational purposes or in a legal context, such as penetration testing on systems for which you have explicit authorization. Any malicious use is prohibited.
