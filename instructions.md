Remove Existing SSH Keys:
rm ~/.ssh/id_rsa
rm ~/.ssh/id_rsa.pub

Generate New SSH Key:
ssh-keygen -t rsa -b 4096 -C "your-new-email@example.com"
(Press Enter when asked for file location)

Start SSH Agent:
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa

Copy New Public Key:
cat ~/.ssh/id_rsa.pub

Add SSH Key to GitHub:
1. Go to GitHub Settings
2. Navigate to "SSH and GPG keys"
3. Click "New SSH key"
4. Paste your copied public key

Update Git Config:
git config --global user.name "Your GitHub Username"
git config --global user.email "your-email@example.com"

Test Connection:
ssh -T git@github.com

Troubleshooting:
- If permission denied, ensure SSH key is added to correct GitHub account
- If push fails, check remote URL: git remote -v
- To update remote URL: git remote set-url origin git@github.com:username/repository.git

Note: Keep your private key (id_rsa) secure and never share it. Only share the public key (id_rsa.pub).



