# Performance Benchmark: Node.js vs Bun

This document details the steps to perform a load test on an Express application using the `oha` tool. The goal is to compare the server performance running on Node.js versus Bun.

## Requirements

To run this test, make sure you have the following installed:

- Node.js
- Bun
- oha

## Initial Setup

Before running the tests, install the necessary dependencies:

```bash
npm install
```

## Test Execution

Below is detailed how to run the server and the 500,000-request stress test for each environment. 

### 1. Test with Node.js

Step 1: Start the server using Node.js in a terminal.

```bash
node express.mjs
```

Step 2: Open a second terminal and launch the load test with `oha`.

```bash
oha http://localhost:3000 -n 500000 -H "Accept-Encoding: identity"
```

### 2. Test with Bun

Step 1: Start the server using Bun in a terminal.

```bash
bun run express.mjs
```

Step 2: In the second terminal, run exactly the same load test.

```bash
oha http://localhost:3000 -n 500000 -H "Accept-Encoding: identity"
```
