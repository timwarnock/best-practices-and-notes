# Notes on Resiliency

Using RDS, we can easily achieve Active-Active for all read requests, and Active-Passive for al write requests.

Multi-AZ will provide high-availability and no data loss (barring catastrophic failure of us-east-1). In the event of catatrophic failure, TPM wold need to:

+ promote RDS replica to master
+ swap route53
+ activate lambda and SQS

Both the API and UI layer simply need to be deployed as standby (or as read-only depending on the routing rules).
