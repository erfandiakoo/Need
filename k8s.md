# Merge the new kubeconfig file to your default kubeconfig file
- KUBECONFIG=~/.kube/config:/path/to/your/new-kubeconfig.yaml kubectl config view --merge --flatten > ~/.kube/config
- nano ~/.zshrc
- export PATH="$PATH:/Users/yourusername/bin"
- source ~/.zshrc
- brew install helm
