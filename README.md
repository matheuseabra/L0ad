# L0ad 🏋

L0ad is a simple toolkit for Load Testing HTTP Servers, it uses Bash for scripting, ApacheBench for benchmarking, CSV for serializing data and GNUplot for plotting benchmark data on bar charts. 

## Quickstart

### Pre-requisites

In order for L0ad to function properly, you need the following properly installed on your machine: 

- Bash
- ApacheBench
- GNUplot
    
### Usage

Within your project's `./bin` directory, run: 

```
$ ./ab <requests> <concurrency> http[s]:/hostname[:port]/path
```

Example: 

```
$ ./ab 1000 100 https://www.nytimes.com/

Bechmarking https://www.nytimes.com/

This might take a while...
```

It benchmarks the New York Times website with a thousand requests and a hundred concurrent users.

**Tip:** take a look at the `/samples` folder to see a sample load test result and its reports.

### Parameters

Parameter | Description
--- | ---
Requests | Number of requests to perform for the benchmarking session.
Concurrency | Number of multiple requests to perform at a time.
Host Address | Host Address URL used for ApacheBench. (It accepts custom ports and enpoints as well)

### Metrics tested

Currently, there are four metrics that are being benchmarked:

1. Average number of requests (sec)
2. Average time per request (ms)
3. Average time per concurrent request (ms)
4. Transfer Rate (Kbytes/sec)

**Obs:** : L0ad iterates 100 times for each metric so that it has a baseline for realistic traffic emulation. (This will be refactored soon)

### Roadmap

The project is still in its early stage and there's a lot of room for improvement.

1. DRYer script reuse 
2. Divide metrics tested to separate scripts
3. Generate benchmark reports dynamically
4. Support for more AB parameters

### Tools used

- Bash
- ApacheBench
- CSV
- GNUplot

### Contributing

Contributions are welcomed, please open a issue.

### License

This project is licensed under the **GNU GPLv3** license.
