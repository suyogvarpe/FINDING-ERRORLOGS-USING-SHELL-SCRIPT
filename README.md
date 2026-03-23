# FINDING-ERRORLOGS-USING-SHELL-SCRIPT
This project included how to find the Error logs from particular error file using shell script.
Steps to create this project

Steps
1)Create Ec2 instance and connect it
2)Create Log file on this server Error.log
  Write following code 
  echo "Application started" >> Error.log
  echo "ERROR: Database connection failed" >> Error.log
3)Create shell script to run grap the error.
  Monitor.sh
4)Add following shell script code in Monitor.sh file (Add error file name so this file search error logs in Error.log file)

  #!/bin/bash

LOG_FILE="Error.log"

if grep -i "ERROR" $LOG_FILE
then
    echo "Error found in log file!"
else
    echo "No issues found"
fi

5)Give the permision to Monitor.sh file using following commands
  chmod +x monitor.sh
6)Run the file Monitor.sh using following so you can get the actual results from Error.log file

./monitor.sh

7)Output will display as follow.

echo "Application started" >> error.log
echo "ERROR: Database connection failed" >> error.log
Error found in log file!

