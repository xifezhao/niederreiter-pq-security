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

# Fig 5-b

## Smart Grid Communication Encryption Performance Analysis

This project implements performance comparison analysis of different encryption algorithms in smart grid communications.

### Features

- Support for multiple encryption schemes:
  - Niederreiter encryption (simulated implementation)
  - RSA encryption
  - ECC (Elliptic Curve Cryptography)
  - AES (Advanced Encryption Standard)

- Performance metrics analysis:
  - Communication latency
  - Data throughput
  - Computational overhead

- Visualization analysis:
  - Time series plots for each metric
  - Box plots for performance metric distributions

### Dependencies

```python
numpy
matplotlib
cryptography
```

### Installation

```bash
pip install numpy matplotlib cryptography
```

### Usage

1. Import required libraries:

```python
import numpy as np
import matplotlib.pyplot as plt
from cryptography.hazmat.primitives import hashes
from cryptography.hazmat.primitives.asymmetric import rsa, ec, padding
from cryptography.hazmat.primitives.ciphers import Cipher, algorithms, modes
```

2. Create smart grid nodes:

```python
nodes = create_nodes(encryption_type='RSA')  # or 'ECC', 'AES', 'Niederreiter'
```

3. Run performance tests:

```python
latencies, throughputs, overheads = run_experiment(encryption_type)
```

### Main Classes and Functions

#### SmartGridNode Class

```python
class SmartGridNode:
    def __init__(self, node_id, encryption_type='Niederreiter', shared_key=None)
    def generate_keys(self, shared_key=None)
    def encrypt_data(self, data, receiver_public_key)
    def decrypt_data(self, encrypted_data, sender_public_key=None)
    def sign_data(self, data)
    def verify_signature(self, data, signature, sender_public_key, sender_id)
```

#### Helper Functions

```python
def create_nodes(encryption_type)
def run_experiment(encryption_type, num_experiments=50)
```

### Experimental Results

The program generates the following visualization charts:
- Latency time series comparison for each encryption scheme
- Throughput time series comparison for each encryption scheme
- Computational overhead time series comparison for each encryption scheme
- Box plots for latency distribution
- Box plots for throughput distribution
- Box plots for computational overhead distribution

### Implementation Notes

1. Niederreiter encryption is simulated
2. Additional security considerations needed for real-world applications
3. Performance results may vary depending on hardware environment

### Contributing

Issues and improvements are welcome!

### License

MIT License

### Technical Details

#### Encryption Methods
- **RSA**: 2048-bit key size with OAEP padding
- **ECC**: SECP384R1 curve with ECDSA
- **AES**: 256-bit key with CBC mode
- **Niederreiter**: Simulated implementation

#### Performance Metrics
- **Latency**: Total time for encryption, transmission, and decryption
- **Throughput**: Data size processed per second
- **Computational Overhead**: Processing time excluding transmission

#### Security Features
- Digital signatures
- Key generation
- Message authentication
- Secure padding schemes

### Future Improvements

1. Implementation of actual Niederreiter encryption
2. Additional encryption schemes
3. Network condition simulation
4. Security analysis tools
5. Real-time monitoring capabilities
