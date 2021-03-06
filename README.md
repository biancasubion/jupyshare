# JupyShare (now at 1.0.9)
![alt text](https://image.ibb.co/csbNEa/4_GY17m_Po_Rw_W5_Fd_Cy4_XF9b_A.png)

JupyShare lets you release your notebook to the cloud and gives you a public endpoint for it through ngrok.

(Jupyter has access to your filesystem. Ngrok lets you expose localhost directly to the internet. This comes with risks. Please read security section for more info.)

### Motivation
JupyShare is perfect for three things
1.  For freeing you up from the huge hassle of trying to debug jupyter notebooks with friends by taking screenshots or copy pasting (They have full access to your notebook and can save, edit, etc. But again please check the Security section and ONLY GIVE THE LINK TO A TRUSTED FRIEND as they will be able to access your filesystem.)
2.  For showing something cool to a friend without having to tell them to download your masterpiece
3.  To connect to a GPU you have shipped to your Canadian home because electricity there is cheaper

### ToDo
[ ]  Containerize

### Security
Ngrok provides a tunnel to your notebook so you definitely do NOT want to share the complete link (with the token and everything) with the world because any random person would pretty much have access to your own localhost/filesystem and start executing code through jupyter.

Two ways to kill the connection
1.  jupyshare kill
2.  as of 1.0.9, exit the script or wait for the ttl to finish (default is 10 minutes)

[edit] you can close your notebook, but it will only kill the ngrok process when you either run `jupyshare kill` or `jupyshare show` immediately after (~~as of 1.0.7 I didn't write a print statement that it killed the process.~~ 1.0.8 prints it out)

[edit for 1.0.9] The script will stay active for as long as you set the ttl (default is 10 minutes). Exiting the script now kills the ngrok connection.

### Upgrade
If you saw this on reddit you probably have 1.0.8. Please upgrade to 1.0.9 to be able to set a ttl and kill the process when you quit the script.

`pip install jupyshare --upgrade`

### Prerequisites

The only thing necessary for JupyShare is ngrok.

```
brew cask install ngrok
```

### Installing

```
pip install jupyshare
```

### Commands

```
jupyshare release

jupyshare kill

jupyshare show

jupyshare --h or --help

jupyshare --browser BROWSER

jupyshare --ttl TIMEINMINUTES
```

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
