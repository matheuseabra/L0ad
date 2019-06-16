# L0ad 🏋

L0ad is a simple toolkit for Load Testing HTTP servers. It uses Bash for scripting, Apache ab for benchmarking, CSV for data serialization and Gnuplot for plotting bar benchmarked data on bar charts. 

**Tip:** take a look at the `/samples` folder to see a sample load test result and its reports.

## Quickstart

### Pre-requisites

In order to L0ad work properly you need to have the following tools setup on your machine:

- Git Bash
- Apache ab - version 2.4
- Gnuplot - version 5.2

### Clone the repository

```
    git clone https://github.com/matheuseabra/L0ad.git
    cd ./L0ad
```

### Usage

Under the `./bin` directory, run: 

```
$ ./load <requests> <concurrency> http[s]:/hostname[:port]/path
```

### Examples 

Simulate 100 network requests sent by 10 different concurrent users:

```
$ ./load 100 10 https://www.nytimes.com/

Bechmarking https://www.nytimes.com/

This might take a while...
```

Simulate 100 network requests sent by 150 different concurrent users:

```
$ ./load 100 150 https://www.nytimes.com/

Bechmarking https://www.nytimes.com/

This might take a while...
```

Simulate 2700 network requests sent by 90 different concurrent users:

```
$ ./load 2700 90 https://www.youtube.com/feed/trending

Bechmarking https://www.youtube.com/feed/trending

This might take a while...
```

**Obs:** Go easy with the number of requests and concurrency as it might make the host address to timeout. Start with low values, then slowly increase them and observe its results.

### Parameters

Parameter | Description
--- | ---
Requests | Number of requests to perform for the benchmarking session.
Concurrency | Number of multiple requests to perform at a time.
Host Address | Host Address URL used for ApacheBench. (It accepts ports and enpoints).

### Metrics

Currently, four metrics are being benchmarked:

1. Average number of requests (sec)
2. Average time per request (ms)
3. Average time per concurrent request (ms)
4. Transfer Rate (Kbytes/sec)

**Obs:** L0ad iterates 100 times for each metric so that it has a baseline for realistic traffic simuation. (This might be refactored soon).

### Dependencies

- Git Bash
- Apache ab - Apache HTTP server benchmarking tool
- CSV
- Gnuplot

### Roadmap

0. DRYer script reuse 
1. Isolate metrics tested into separate scripts
2. Generate benchmark reports dynamically
3. Support for more AB parameters
4. Support for more gnuplot charts

### Contributing / Feedback

Contributions and feedback are welcomed. 

The project is still in its early stage and there's a lot of room for improvement. If you find one or just have any idea on how to make this tools better, please open an issue.

### License

This project is licensed under the **GNU GPLv3** license.
