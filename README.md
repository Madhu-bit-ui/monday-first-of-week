#!/bin/bash
set -e

echo "Updating system..."
sudo yum update -y

echo "Installing prerequisites..."
sudo yum install -y curl ca-certificates

echo "Installing Node.js 18 LTS..."
curl -fsSL https://rpm.nodesource.com/setup_18.x | sudo bash -
sudo yum install -y nodejs

echo "Verifying Node.js installation..."
node -v
npm -v

echo "Installing Express..."
sudo npm install express

echo "Installing supporting tools (ruby, wget)..."
sudo yum install -y ruby wget

echo "Setup completed successfully!"
echo "You can now run: node app.js"
