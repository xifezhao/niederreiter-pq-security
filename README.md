# niederreiter-pq-security
Implementation of Niederreiter cryptosystem for post-quantum security in complex system simulations. Includes code, data and supplementary materials for the paper published in S&amp;S journal.
# Fig 5-a

## Smart Grid Encryption Communication System

A Python implementation for secure communication between smart grid nodes, supporting multiple encryption schemes.

### Features

- Multiple encryption algorithms support:
  - Niederreiter encryption (Post-quantum cryptography)
  - RSA asymmetric encryption
  - ECC (Elliptic Curve Cryptography)
  - AES symmetric encryption

- Complete encryption communication features:
  - Key generation
  - Data encryption/decryption
  - Digital signatures
  - Signature verification

- Performance evaluation system:
  - Latency measurement
  - Throughput analysis
  - Computational overhead statistics

### Dependencies

```bash
pip install numpy networkx matplotlib cryptography
```

### Usage

```python
# Create nodes
nodes = create_nodes('RSA')  # Options: 'RSA', 'ECC', 'AES', 'Niederreiter'

# Communication example
sender = nodes[1]
receiver = nodes[2]
message = "Hello Grid!"

# Encrypt and sign
encrypted = sender.encrypt_data(message, receiver.public_key)
signature = sender.sign_data(message)

# Decrypt and verify
decrypted = receiver.decrypt_data(encrypted, sender.public_key)
is_valid = receiver.verify_signature(decrypted, signature, sender.public_key, sender.node_id)
```

### Performance Testing

```python
# Run performance tests
latencies, throughputs, overheads = run_experiment('RSA')
```

### Main Classes and Methods

#### SmartGridNode
- `__init__(node_id, encryption_type)`: Initialize node
- `encrypt_data()`: Data encryption
- `decrypt_data()`: Data decryption
- `sign_data()`: Generate digital signature
- `verify_signature()`: Verify signature

### Contributing

Issues and Pull Requests are welcome to improve the code.

### License

MIT License
