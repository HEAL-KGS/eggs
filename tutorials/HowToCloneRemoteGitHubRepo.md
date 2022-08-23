How to Clone A Remote GitHub Repo
---

1. In a terminal window, navigate to the desired directory on your machine. For me, this will look like: 

```bash
cd Desktop\KGS\eggs
```

1. Get the repo link.
    1. From a browser, open the repo on GitHub, click the green Code button, and copy the link (Note that you can use the HTTPS or SSH link depending on how you’ve set up git in your command line. I recommend using SSH keys.)
    2. Alternatively, you can type the link manually if you know the user and the repo name.
2. Back in the terminal, type `$ git clone` followed by the repo link from above. $ git clone git@github.com:USER/REPO.git
    1. For this project, this command will be:
    
    ```bash
    $ git clone git@github.com:HEAL-KGS/eggs.git
    ```