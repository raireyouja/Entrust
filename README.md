# Entrust
1- Load testing with ApacheBench on an HTTP webserver (Nginx)
we execute the following command: 
```
ab http://127.0.0.1/ 
```

This basic command isn’t particularly useful without any additional options, so let’s include some. Apache Bench has a lot of options available, but some of the most useful are:

    -n (number): used to specify the number of requests ab should send to apache 
    -k : Use HTTP KeepAlive feature
    -c (concurrent): used to specify the number of simultaneous requests for ab to make
After executing the following command, using the three flags, with which we are hitting the website with 350 simultaneous connections until 20 thousand requests are met. It will be done using the keep alive header:
```
ab -k -c 350 -n 20000 http://127.0.0.1/
```

We got the following result:
```
This is ApacheBench, Version 2.3 <$Revision: 1843412 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking 127.0.0.1 (be patient)
Completed 2000 requests
Completed 4000 requests
Completed 6000 requests
Completed 8000 requests
Completed 10000 requests
Completed 12000 requests
Completed 14000 requests
Completed 16000 requests
Completed 18000 requests
Completed 20000 requests
Finished 20000 requests


Server Software:        nginx/1.18.0
Server Hostname:        127.0.0.1
Server Port:            80

Document Path:          /
Document Length:        612 bytes

Concurrency Level:      350
Time taken for tests:   0.454 seconds
Complete requests:      20000
Failed requests:        0
Keep-Alive requests:    19903
Total transferred:      17179515 bytes
HTML transferred:       12240000 bytes
Requests per second:    44056.65 [#/sec] (mean)
Time per request:       7.944 [ms] (mean)
Time per request:       0.023 [ms] (mean, across all concurrent requests)
Transfer rate:          36956.63 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   1.9      0      24
Processing:     0    7   8.0      3      37
Waiting:        0    7   8.0      3      26
Total:          0    7   8.1      3      37

Percentage of the requests served within a certain time (ms)
  50%      3
  66%      9
  75%     14
  80%     16
  90%     21
  95%     23
  98%     24
  99%     25
 100%     37 (longest request)

```
