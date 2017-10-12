Overview of work done:

I created a gcp instance, installed python3 and all the required packages and moved my 3 scripts over to the cloud server. Nothing is currently running of my local machine.  

I will go over limitations and things I would do next if this was a production environment:

1. Update scripts to do basic logging. This will enable me to have a signal for the next script that everything was done properly within the first script.

2. Setup cron jobs.

3. Add notification emails/texts upon failures, so that I can log in and fix whatever is broken.

4. Add google’s cloud based NAS for storage of files.

5. Setup  some kind of external server monitoring job ( I am guessing platform has something built in if not there is a number of services that can ping the server make sure it is up and not dead ) and send out notifications in case server is irresponsive. 

6. If I am dealing with new data daily, I would add checks to insure the scoring results are sane, so this will depend on the data, but for example I have 80% accuracy right now, so assuming this is an average expected result, I would add a check if score drops below 60% or 50%, so that even if all the steps completed successfully, something could have failed with model or data was somehow not accurate resulting in bad predictins. 

6. Additionally I would setup systems monitoring I would watch for things like RAM, CPU utilization and hard drive space available ( latter can have nasty unexpected effects from my experience local drive can get full fast if something is broken and flooded with logs, effects are random and not clear right away )


In current standalone setup I believe this will be sufficient, if there is more interaction with other infrastructure or application pipeline components we can put more checks in place.
