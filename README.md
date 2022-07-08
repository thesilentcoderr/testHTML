# testHTML
-> Used two ec2-instances one for dev and anf for prod\
-> In dev jenkins, httpd and git was installed and configured.\
-> index.html is treated as the home page in httpd at location /var/www/html.\
-> Jenkinsfile was created to create a declarative pipeline\
-> Stages:-\
<pre>
      1) Git Fetch - Fetching the git repository
      2) Build - As there is no build required in html websites so directly copying 
                  to dev server(same as jenkins in my case)
      3) Test - UAT team will review the dev env working if problem persists then 
                they will ABORT the pipeline else PROCEED it to execute next pipe.
      4) Deploy - In this stage I use Publish over SSH plugin so I configure it first
                  by putting the details of the connecting(prod) env and putting public key
                  of server(dev) in authorized_keys files for configuration purpose.
                  The configuration is done as all the files in the jenkins current workspace
                  are moved to /var/www/html folder of prod. 
 </pre>
