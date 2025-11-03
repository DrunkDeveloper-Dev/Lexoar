# Tensora L2

AI Layer 2 built on BNB Chain using the OP Stack.

## Configuration

- **Chain ID**: 44444444
- **L1**: BNB Smart Chain (BSC)
- **Technology**: OP Stack
- **Explorer**: https://explorer.tensora.sh

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

## Contract Addresses

- **L1 Standard Bridge**: 0xD9fa19FaC816a336230af459aB2C7Ed55072Cc4c
- **Optimism Portal**: 0x5D99EDfF294E8E31f0b038Ef844267f7952850AA
- **System Config**: 0x257BE5F8C79061edAcF64C4a3aBe5C316f274Fe3

## Files Structure

## Quick Start

```bash
# Clone the repository
git clone <your-repo-url>
cd tensora-l2

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
