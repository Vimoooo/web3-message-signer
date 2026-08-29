const { ethers } = require("ethers");

const wallet = ethers.Wallet.createRandom();
const message = "Hello Web3!";

async function main() {
  const signature = await wallet.signMessage(message);
  const recovered = ethers.verifyMessage(message, signature);

  console.log("Wallet:", wallet.address);
  console.log("Message:", message);
  console.log("Signature:", signature);
  console.log("Verified:", recovered === wallet.address);
}

main();
