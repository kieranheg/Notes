# MongoDB Notes

See https://docs.mongodb.com/master/tutorial/install-mongodb-on-ubuntu/?_ga=1.150036470.153110113.1469897795

## Start MongoDB.¶

`$ sudo service mongod start`

## Verify that MongoDB has started successfully

Verify that the mongod process has started successfully by checking the contents of the log file at /var/log/mongodb/mongod.log for a line reading

[initandlisten] waiting for connections on port <port>

where <port> is the port configured in /etc/mongod.conf, 27017 by default.

## Stop MongoDB.¶

`$ sudo service mongod stop

## Restart MongoDB.¶

`$ sudo service mongod restart`

## Getting Started with MongoDB (Node.js Edition) https://docs.mongodb.com/getting-started/node/

