# Lexora L2

AI Layer 2 built on Solana Chain using the OP Stack.

## Configuration

- **Chain ID**: 5eykt4UsFv8P8NJdTREpY1vzqKqZKvdp
- **L1**: Solana (SOL)
- **Technology**: OP Stack
- **Explorer**: https://explorer.lexora.com

## Setup

1. Copy `.env.example` to `.env`
2. Fill in your mnemonic phrases
3. Run `docker-compose up -d`

## Architecture

- **op-geth**: L2 execution client
- **op-node**: L2 consensus client  
- **op-batcher**: Submits batches to L1
- **op-proposer**: Proposes state roots
- **Blockscout**: Blockchain explorer

## Performance

- **Current TPS**: ~1.4 TPS
- **Theoretical Max**: 714 TPS
- **Block Time**: ~0.65 seconds
- **Finality**: ~2 seconds

## Files Structure

## Quick Start

```bash
# Clone the repository
git clone <your-repo-url>
cd lexora-l2

# Set up environment
cp .env.example .env
# Edit .env with your mnemonic phrases

# Start the L2
docker-compose up -d

# Check status
curl -X POST http://localhost:8545 \
  -H "Content-Type: application/json" \
  -d '{"jsonrpc":"2.0","method":"eth_blockNumber","params":[],"id":1}'
```

## Monitoring

Use the included scripts to monitor your L2:

```bash
# Check L2 health
./check_l2_health.sh

# Simple status check
./check_l2_simple.sh

# Check sync status
./check_sync_status.sh
```
