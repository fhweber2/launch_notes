### Jason from Backupify

Databases - all run from EC2 (an email backup sys):

                    |

Redis       - worker bee, jobs, etc  (very fast )

                    |

Postgresql     - 10 GB of data  (the need to optimize SQL queries)

                    |

Casandra    - stripped email headers, etc.  about 1.5 TB  (takes time to index & obtain data from queries)

                    |
S3  -  Petabyte  - 

The problem is the speed to query data down the chain

Recommends not to use Resque rather use Sidekick

Once you have these stacks they must be maintained.... 



