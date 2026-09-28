# KREW INSTALL
# Make sure git is installed.
## Windows

Download `krew.exe` and place it in the following directory:

```text
C:\kubectl-krew-ai
```

Open **Command Prompt as Administrator** and navigate to the directory:

```cmd
cd C:\kubectl-krew-ai
```

Install Krew:

```cmd
.\krew.exe install krew
```

## Add Krew to PATH

Go to:

**Environment Variables → User variables → Path → Edit → New**

Add:

```text
%USERPROFILE%\.krew\bin
```

> Add it under **User variables → Path**. You do not need to add it under **System variables → Path**.

Close the Command Prompt and open a **new** Command Prompt.

## Verify Krew Installation

Check the Krew installation:

```cmd
kubectl krew
```

Check the Krew version:

```cmd
kubectl krew version
```

Check the Krew executable location:

```cmd
where kubectl-krew
```

---

# macOS

Make sure that `git` is installed.

Check Git:

```sh
git --version
```

## Install Krew

Run the following command to download and install Krew:

```sh
(
  set -x; cd "$(mktemp -d)" &&
  OS="$(uname | tr '[:upper:]' '[:lower:]')" &&
  ARCH="$(uname -m | sed -e 's/x86_64/amd64/' -e 's/\(arm\)\(64\)\?.*/\1\2/' -e 's/aarch64$/arm64/')" &&
  KREW="krew-${OS}_${ARCH}" &&
  curl -fsSLO "https://github.com/kubernetes-sigs/krew/releases/latest/download/${KREW}.tar.gz" &&
  tar zxvf "${KREW}.tar.gz" &&
  ./"${KREW}" install krew
)
```

## Add Krew to PATH

Add the `$HOME/.krew/bin` directory to your PATH environment variable.

For **Zsh**, update the `.zshrc` file:

```sh
nano ~/.zshrc
```

For **Bash**, update the `.bashrc` file:

```sh
nano ~/.bashrc
```

Append the following line:

```sh
export PATH="${KREW_ROOT:-$HOME/.krew}/bin:$PATH"
```

Save the file and restart your shell.

Alternatively, reload the configuration without restarting:

For Zsh:

```sh
source ~/.zshrc
```

For Bash:

```sh
source ~/.bashrc
```

## Verify Krew Installation

Run:

```sh
kubectl krew
```

Check the Krew version:

```sh
kubectl krew version
```

Check the Krew executable location:

```sh
which kubectl-krew
```

The expected location is similar to:

```text
/Users/<your-username>/.krew/bin/kubectl-krew
```

---

# PATH Summary

| Operating System | Krew PATH                 | Configuration             |
| ---------------- | ------------------------- | ------------------------- |
| Windows          | `%USERPROFILE%\.krew\bin` | User → Path               |
| macOS            | `$HOME/.krew/bin`         | `~/.zshrc` or `~/.bashrc` |