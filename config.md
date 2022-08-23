global:
    api-listen-addr: :5183
    timeout: 300s
    memo: Mr Keim#1112
    light-cache-size: 20
chains:
    GAIA:
        type: cosmos
        value:
            key: $gaia-rly
            chain-id: $DST_CHAIN
            rpc-addr: http://138.201.139.207:21657
            grpc-addr: http://138.201.139.207:1090
            account-prefix: cosmos
            keyring-backend: test
            gas-adjustment: 1.2
            gas-prices: 0.0025uatom
            debug: true
            timeout: 300s
            output-format: json
            sign-mode: direct
            memo-prefix: Mr Keim#1112
    STRIDE-TESTNET-4:
        type: cosmos
        value:
            key: $stride-rly
            chain-id: $SRC_CHAIN
            rpc-addr: http://localhost:26657
            grpc-addr: http://localhost:6060
            account-prefix: stride
            keyring-backend: test
            gas-adjustment: 1.2
            gas-prices: 0.0025ustrd
            debug: true
            timeout: 300s
            output-format: json
            sign-mode: direct
            memo-prefix: Mr Keim#1112
paths:
    STRIDE-GAIA:
        src:
            chain-id: $DST_CHAIN
            client-id: 07-tendermint-0
            connection-id: connection-0
        dst:
            chain-id: $SRC_CHAIN
            client-id: 07-tendermint-0
            connection-id: connection-0
        src-channel-filter:
            rule: "allowlist"
            channel-list: [channel-0, channel-1, channel-2, channel-3, channel-4]
EOF
