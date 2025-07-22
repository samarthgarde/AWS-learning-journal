# Whitelisting an IP Address

To allow access only from your specific IP address (for SSH, HTTP, etc.):

1. Go to **AWS Console** → **EC2** → **Security Groups**.
2. Find and select the Security Group attached to your EC2 instance.
3. Click on **Inbound Rules** → **Edit Inbound Rules**.
4. Add or modify a rule:
   - **Type:** SSH
   - **Protocol:** TCP
   - **Port Range:** 22
   - **Source:** My IP (or Custom → `YOUR.IP.ADDRESS/32`)

5. Use `/32` to allow **only that specific IP**.



