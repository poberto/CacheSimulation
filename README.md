# Cache Simulator

A multi-level, set-associative cache simulator with configurable latencies, block sizes, and hierarchy depth. Built as a computer architecture project at the University of Pittsburgh.

## Features

- **N-level cache hierarchy** with independent size, latency, and associativity per level
- **Set-associative mapping** with configurable associativity per cache level
- **LRU eviction policy** across all cache levels
- **Write-back and write-through** support with write-allocate / non-write-allocate policies
- **Hit/miss ratio tracking** per cache layer
- **Access latency calculation** with memory access penalty

## Usage

```
python cache_sim.py
```

The simulator prompts for cache configuration:
- Number of cache levels
- Size per level (e.g., `4KB`, `256KB`, `1MB`)
- Access latency per level (clock cycles)
- Block size (bytes)
- Set associativity per level
- Write policy (write-back + write-allocate or write-through + non-write-allocate)

Place instruction traces in `Input_Data/` — each line contains an operation (`r`/`w`), a memory address, and an arrival time.

## Architecture

- `cache.py` — Core cache logic: address parsing (tag/index/offset), read/write operations, LRU management, data loading, and hit/miss tracking
- `cache_sim.py` — CLI interface and configuration

Built with Python.
