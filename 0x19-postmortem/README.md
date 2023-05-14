POSTMORTEM.

A brief summary of the issue was complete unavailability, including the API made available for integration by third parties. On each and every request made to the platform routes by users, error 500 showed up. During the outage, all users were unable to use the services.

Timeline.

10:00 AM The team checks error logs 
10:27 AM Updated configuration to log more errors
10:45 AM Filename mistake detected in configuration file
10:57 AM Run the Puppet manifest command on all the servers.
11:02 AM Fully recovered and online

The Root cause and Resolution.

The site went down after a minor update that affected the entire site was rolled out without being tested first. When we discovered that there were no errors in our 'error.log' files, we changed our configuration file to enable further error logging. Using 'strace,' it was discovered that issues occurred when the site was requested due to an unintentional filename misspelling. In keeping with standard protocol, the server tried to locate the file but was unsuccessful since it was looking for the ".phpp" file rather than the ".php" one. Tests successfully displayed the website after this line in the "/var/www/html/wp-settings.php" file was changed. To immediately resume service, a puppet manifest was created and run across all corporate servers.

The Corrective and Preventative Measures.

- Implement a redundant architecture with numerous application servers and load-balancing technologies to evenly distribute traffic. By doing this, high availability is guaranteed, and the effects of a single server failure are reduced.
- Implement reliable monitoring systems that continuously track the performance and health of application servers. Create alerts to immediately inform the operations team of any unusual activity or serious mistakes.
- Mechanisms for failover In the event that a primary server fails, configure failover procedures to automatically reroute traffic to a backup server. This reduces downtime and enables flawless service continuity.

