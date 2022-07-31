# LuksOracle

Chainlink oracle on Lukso blockchain which supports API uint256 GET requests.


## Starting the Chainlink node on Lukso with WSS RPC URL:

1. Create an ".env" file inside the "chainlink-lukso" directory with the following in chainlink-lukso [we are using a public WSS RPC URL]:
    
        ROOT=/chainlink
        LOG_LEVEL=debug
        ETH_CHAIN_ID=2828
        CHAINLINK_TLS_PORT=0
        SECURE_COOKIES=false
        ALLOW_ORIGINS=*
        ETH_URL=wss://ws.rpc.l16.lukso.network
        DATABASE_URL=postgresql://postgres:secret@chainlink-lukso-pg_chainlink-1:5432/chainlink-lukso?sslmode=disable

2. Update directories to match your file system for "docker-compose.yml"
3. Run the following in command line:

        cd chainlink-lukso
        docker compose up

:warning: Note: if there is an issue with your node, run the following (will wipe DockerPostgreSQL files for a clean node): :warning:

        cd chainlink-lukso
        docker rm -vf $(docker ps -aq)
        docker rmi -f $(docker images -aq)
        sudo rm -r -f data

4. Interact with Chainlink node interface in weB browser URL:

        http://localhost:6688/

## Lukso Chainlink Contracts

Lukso LINK: https://explorer.execution.l16.lukso.network/address/0xbFB26279a9D28CeC1F781808Da89eFbBfE2c4268/transactions

(From Ethereum Mainnet LINK: https://etherscan.io/token/0x514910771af9ca656af840dff83e8264ecf986ca#code)

Faucet deployed (redeploy after all LINK drained since contract edited):
https://explorer.execution.l16.lukso.network/address/0x98464Aa91399563c9DD4652867B87b2C088F9660/transactions

:red_circle: Lukso Oracle.sol (redeploy and save contract): :red_circle:

:red_circle: Lukso requestGETuint256.sol (redeploy and save contract): :red_circle:
