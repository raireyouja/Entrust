# Entrust
1- Load testing with ApacheBench on an HTTP webserver (Nginx)
we execute the following command: 
  #ab http://127.0.0.1/

This basic command isn’t particularly useful without any additional options, so let’s include some. Apache Bench has a lot of options available, but some of the most useful are:

    -n (number): used to specify the number of requests ab should send to apache
    -k : Use HTTP KeepAlive feature
    -c (concurrent): used to specify the number of simultaneous requests for ab to make
