# benchmark_mod_mam
## How to Use
- Install Tsung if not installed yet (http://tsung.erlang-projects.org/user_manual/installation.html)
- Tsung .xml files located in testN-mysql and testX-cassandra
- Setup host names used in each .xml files (cassandra-riak-1,cassandra-riak-2,cassandra-riak-3,ejabberd_aws)
- Add public key (if not added yet) of the ec2 instance used by Tsung to authorized_keys on each mentioned hosts
- Ec2 instance of cassandra and riak are 'cassandra-riak-X's, instance for Ejabberd server is 'ejabberd', and instance for Tsung is 'spammer'  
- Run tsung : `$tsung -f filename.xml start`
- Generate report: enter tsung's log directory, enter directory of the test, 
       <br>then run `$/usr/lib/tsung/bin/tsung_stats.pl` (some dependencies might be needed)
- Generate plot for comparing test results: 
      <br>`$tsplot -c conf.conf -v "Test1" test1dir/tsung.log "Test2" test2dir/tsung.log -d outputdir` (some dependencies might be needed)
- To use your own test scenario, modify the .xml file
