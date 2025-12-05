### DePIN Network

#### 一、Project Structure
```bash
depin-network-final/
├── depin-backend/              # Go + Gin
├── jeecg-boot-master/          # SpringBoot data backend
├── jeecgboot-vue3-master/      # Vue3
```

#### 二、Deploy（Need Server服务器 to deploy all the projects)

```bash

git clone https://github.com/yourname/depin-network-final.git
cd depin-network-final


cp .env.example .env

RPC_URL=https://opt-sepolia.g.alchemy.com/v2/your-key
ORACLE_PRIVATE_KEY=0x...                         
CONTRACT_NFT=0x...
CONTRACT_REWARD=0x...
DATABASE_URL=postgres://depin:depin@localhost:5432/depin


docker-compose up -d


cd contracts
npm install
npx hardhat run scripts/deploy.js --network optimismSepolia


cd ../jeecg-boot-master && mvn spring-boot:run &

cd ../jeecgboot-vue3-master
npm install
npm run dev
```

