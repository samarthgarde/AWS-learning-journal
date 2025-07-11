##è Launch EC2 Instance

1. Go to AWS Management Console ‚Üí EC2.
2. Click **Launch Instance**.
3. Choose:
   - **Amazon Linux 2** / Ubuntu
   - Instance Type: `t2.micro` (Free Tier)
4. Configure:
   - Key Pair: Select or create a new one.
   - Network: Assign public IP
   - Storage: Default (8 GB)
   - Security Group: Allow SSH (port 22), HTTP (port 80), HTTPS (443)
5. Launch the instance and wait for it to initialize.

## connectivity SSH Into EC2 Instance:
cd C:\Users\Samarth\Downloads
icacls "keypair.pem" /inheritance:r /grant:r "%USERNAME%:R"
ssh -i "keypair.pem" ubuntu@<ip adress>

DONE

