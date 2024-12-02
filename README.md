# niederreiter-pq-security
Implementation of Niederreiter cryptosystem for post-quantum security in complex system simulations. Includes code, data and supplementary materials for the paper published in S&amp;S journal.
# Fig 5-a

## Smart Grid Communication Simulator

A Python-based simulator for analyzing secure communication in smart grid networks, featuring basic encryption and performance analysis.

### Features

- Basic encryption simulation:
  - Public/private key generation
  - Data encryption/decryption
  - Digital signatures
  - Signature verification

- Network topology:
  - Graph-based network representation
  - Configurable node connections
  - Flexible network structure

- Performance metrics:
  - Latency measurement
  - Throughput analysis
  - Computational overhead tracking
  - Statistical analysis

### Dependencies

```bash
pip install numpy networkx matplotlib
```

### Usage

#### Basic Node Creation
```python
# Create a node
node = SmartGridNode(1)

# Create multiple nodes
nodes = {}
for i in range(1, 6):
    nodes[i] = SmartGridNode(i)
```

#### Communication Example
```python
# Send data between nodes
sender = nodes[1]
receiver = nodes[3]
data = "PowerData"

# Encrypt and sign
encrypted_data = sender.encrypt_data(data, receiver.public_key)
signature = sender.sign_data(data)

# Decrypt and verify
decrypted_data = receiver.decrypt_data(encrypted_data)
is_valid = receiver.verify_signature(decrypted_data, signature, sender.node_id)
```

#### Performance Testing
```python
# Run performance tests
num_experiments = 500
for _ in range(num_experiments):
    # Simulation code here
    pass

# Generate performance graphs
plt.figure(figsize=(15, 4))
# Plot latency, throughput, and computational overhead
```

### Main Components

#### SmartGridNode Class
- `__init__(node_id)`: Initialize node
- `encrypt_data()`: Simulate data encryption
- `decrypt_data()`: Simulate data decryption
- `sign_data()`: Generate digital signatures
- `verify_signature()`: Verify signatures

#### Performance Metrics
- Latency (ms)
- Throughput (characters/second)
- Computational overhead (ms)

### Visualization

The simulator includes visualization tools for:
- Network topology
- Performance metrics distribution
- Statistical analysis results

### Contributing

Feel free to contribute by:
- Reporting bugs
- Suggesting enhancements
- Submitting pull requests

### License

MIT License
