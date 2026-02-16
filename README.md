# vivaldi

Standalone Go module for [Vivaldi network coordinates](https://dl.acm.org/doi/10.1145/1030194.1015471).

Forked from [`hashicorp/serf/coordinate`](https://github.com/hashicorp/serf/tree/master/coordinate)
to provide a zero-dependency importable module without pulling in the full serf dependency tree.

## Usage

```go
import "github.com/wjordan/vivaldi"

// Create a client with default 8-dimensional config
client, err := vivaldi.NewClient(vivaldi.DefaultConfig())

// On each RTT observation from a peer:
coord, err := client.Update("peer-id", peerCoordinate, observedRTT)

// Estimate RTT to any node whose coordinate you know:
estimatedRTT := client.DistanceTo(otherCoordinate)
```

## License

Original code copyright HashiCorp, Inc. Licensed under MPL-2.0.
