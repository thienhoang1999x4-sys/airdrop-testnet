# EVM Airdrop Testnet Tool 🎁

Công cụ phân phối airdrop trên testnet EVM (Ethereum, Sepolia, Polygon Mumbai, v.v.) cho ví Web3.

## 🚀 Tính năng

- ✅ Deploy smart contract token ERC20
- ✅ Deploy smart contract phân phối airdrop
- ✅ Batch set claim amounts cho nhiều địa chỉ
- ✅ Quản lý trạng thái airdrop (active/inactive)
- ✅ Verify airdrop status
- ✅ Recover tokens
- ✅ Check wallet balance

## 📋 Yêu cầu

- Node.js >= 16
- Hardhat
- Testnet RPC URL
- Private key (không share công khai!)

## 🔧 Cài đặt

```bash
git clone https://github.com/thienhoang1999x4-sys/airdrop-testnet.git
cd airdrop-testnet
npm install
```

## ⚙️ Cấu hình

1. **Copy file `.env.example` thành `.env`:**

```bash
cp .env.example .env
```

2. **Cập nhật các biến trong `.env`:**

```env
# Sepolia testnet
RPC_URL=https://sepolia.infura.io/v3/YOUR_INFURA_KEY
PRIVATE_KEY=your_private_key_without_0x
ETHERSCAN_API_KEY=your_etherscan_key
```

3. **Cập nhật danh sách recipients trong `data/recipients.json`:**

```json
[
  {
    "address": "0x742d35Cc6634C0532925a3b844Bc9e7595f42bE0",
    "amount": "100"
  },
  {
    "address": "0x8ba1f109551bD432803012645Ac136ddd64DBA72",
    "amount": "100"
  }
]
```

## 🎯 Sử dụng

### 1. Compile Smart Contracts

```bash
npm run compile
```

### 2. Deploy Contracts

```bash
npm run deploy
```

**Output:**
- Token contract address
- Distributor contract address
- Deployment info lưu trong `deployments.json`

### 3. Thiết lập Airdrop

```bash
npm run airdrop
```

**Điều này sẽ:**
- Set claim amounts cho tất cả recipients
- Kích hoạt airdrop
- Lưu info trong `airdrop-info.json`

### 4. Verify Airdrop

```bash
npm run verify
```

**Hiển thị:**
- Token balance trong distributor
- Trạng thái airdrop
- Tổng đã phân phối

### 5. Check Wallet Balance

```bash
npm run check-balance
```

## 📝 Smart Contracts

### AirdropToken (ERC20)

- Tạo token với supply ban đầu
- Cho phép owner mint thêm tokens
- Burn functionality

### AirdropDistributor

- Quản lý danh sách nhận tokens
- Cho phép user claim tokens
- Batch set claim amounts
- Activate/Deactivate airdrop
- Recover tokens

## 🔒 Bảo mật

- ⚠️ **KHÔNG** share private key công khai
- ⚠️ Sử dụng `.env` và `.gitignore` để bảo vệ credentials
- ✅ Smart contract có ReentrancyGuard
- ✅ Chỉ owner mới có thể config

## 📊 Hỗ trợ các testnet

- **Sepolia** (Ethereum testnet)
- **Polygon Mumbai**
- **Goerli** (deprecated)

## 🛠️ Troubleshooting

### RPC Error
```bash
# Kiểm tra RPC URL trong .env
RPC_URL=https://sepolia.infura.io/v3/YOUR_KEY
```

### Insufficient Balance
```bash
# Check balance
npm run check-balance

# Lấy testnet tokens từ faucet
# Sepolia: https://sepoliafaucet.com
# Mumbai: https://faucet.polygon.technology/
```

### Contract Already Deployed
```bash
# Xóa deployments cũ
rm deployments.json airdrop-info.json
npm run deploy
```

## 📚 Tài liệu thêm

- [Hardhat Docs](https://hardhat.org/docs)
- [OpenZeppelin Contracts](https://docs.openzeppelin.com/contracts/)
- [Ethers.js](https://docs.ethers.org/)

## 📞 Support

Gặp vấn đề? Tạo issue trên GitHub repo.

## 📄 License

MIT

---

**Created by:** thienhoang1999x4-sys  
**Last updated:** 2026-06-24
