# Pipe-Network-DevNet-2-Node-Run-Full-guide
# Introduction
Pipe Network is transforming media streaming with a decentralized Content Delivery Network (CDN) on Solana’s high-performance blockchain. This secure, scalable, and hyper-localized solution enables permissionless contributors to deploy Points of Presence (PoPs) in targeted regions, ensuring lightning-fast access to high-quality media and real-time applications.

By removing the need for costly centralized infrastructure, Pipe Network enables rapid scaling and unmatched content streaming. The network offers the essential infrastructure for developers, operators, and content providers to thrive in the digital age.

Pipe Network aims to create a hyper-localized, scalable CDN that leverages Solana’s high-performance blockchain to deliver content faster, more securely, and more efficiently than traditional centralized CDNs, such as Cloudflare. The project incentivizes users to host internet infrastructure by running nodes, contributing to a decentralized ecosystem. This approach is part of a broader trend in decentralized infrastructure networks (DePIN), which seek to distribute and democratize access to digital services.
# Key features of Pipe Network include
* Permissionless Participation: Anyone can contribute to the network by running nodes, known as PoP (Point of Presence) nodes, without needing special permissions. This fosters a community-driven ecosystem.
* Low-Latency Content Delivery: By placing nodes close to end users, Pipe Network ensures fast and reliable content streaming, making it suitable for media and real-time applications.
* Guardian Node Program: Pipe Network has introduced a program where users can earn points by running a Guardian Node via a browser extension. These points are intended to convert into rewards after the project’s token generation event (TGE), though the specifics of the rewards and tokenomics are not fully detailed in the available information.
* Funding and Backing: Pipe Network has raised $10 million in funding, with investments led by Multicoin Capital and Solana Ventures, indicating strong industry support and interest in its vision.

# Funding Source
1️⃣ Check: https://cryptorank.io/ico/pipe-network#funding-rounds
<br>2️⃣ Check: https://sosovalue.com/project/pipe-network-1844240875785244674

# CLI Node Run Full Guide (PC and VPS for Both)
Offical Docs by Pipe Network - https://docs.pipe.network/devnet-2

1️⃣ Dependencies for WINDOWS & LINUX & VPS
```
sudo apt update
sudo apt upgrade -y
```

For VPS Only
```
apt install screen -y
```

2️⃣ Download Some Files
```
curl -L -o pop "https://dl.pipecdn.app/v0.2.8/pop"
```
```
chmod +x pop
```

For VPS Only
```
screen -S pipe
```

3️⃣ Make Directory (create folder to be used for download cache)
```
mkdir download_cache
```

4️⃣ Signup Your Account
```
./pop --signup-by-referral-route d2be19523a45a241
```

```
# Generate Your Referral
./pop --gen-referral-route
```

5️⃣ Start Node
```
./pop --ram 8 --max-disk 500 --cache-dir /data --pubKey <KEY>
```

OR
```
./pop \

--ram 8 \              # RAM in GB

--max-disk 500 \       # Max disk usage in GB  

--cache-dir /data \    # Cache location

--pubKey <KEY>         # Solana public key (Address)
```

Note: Put your `ram` , `disk` & `pubkey` with your actual Information.Retrieve the public key from your Solana wallet (e.g., Phantom, Backpack) & Replace in `<KEY>` by Solana Address

![6165852026936868478](https://github.com/user-attachments/assets/6ceac486-a639-48ed-aa81-cccfbe02d6da)

If Your Node showing this Above Error then Put Below Command (Must Put `ram` , `disk` & `pubkey` value)
```
sudo ./pop --ram 8 --max-disk 500 --cache-dir /data --pubKey <KEY>
```

# Open Another Window for WSL or VPS

## Save the file
```
nano ~/node_info.json
```

## Monitor your Node Status & Points
```
./pop --status
```
```
./pop --points
```

## Check Points & Status from Dashboard - https://dashboard.pipenetwork.com/node-lookup


## 🔶For Next Day Run This Command

#1 Open WSL and Put this Command 
```
sudo ./pop --ram 8 --max-disk 500 --cache-dir /data --pubKey <KEY>
```

Note: Replace your `ram` , `disk` & `pubkey` with your actual Information.Retrieve the public key from your Solana wallet (e.g., Phantom, Backpack)

## Upgrade Your Node in v0.2.8

1️⃣ Upgrade (Download Latest Version)
```
curl -L -o pop "https://dl.pipecdn.app/v0.2.8/pop"
```
```
chmod +x pop
```

2️⃣ Start Node
```
sudo ./pop --ram 8 --max-disk 500 --cache-dir /data --pubKey <KEY>
```

Note: Put your `ram` , `disk` & `pubkey` with your actual Information.Retrieve the public key from your Solana wallet (e.g., Phantom, Backpack) & Replace in `<KEY>` by Solana Address

## Need to Free Your 8003 Port

### Identify the Process Using Port 8003
```
sudo ss -tulpn | grep 8003
```

Example - ``` LISTEN  0  128  0.0.0.0:0380  0.0.0.0:*  users:(("nginx",pid=1234,fd=6)) ```

### Terminate the Process by PID
```
sudo kill -9 1234
```

### Kill All Processes Using Port 8003
```
sudo fuser -k 8003/tcp
```



