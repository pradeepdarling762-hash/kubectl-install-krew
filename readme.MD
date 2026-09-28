# KREW INSTALL

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

Add the following path to:

**Environment Variables → User variables → Path → Edit → New**

```text
%USERPROFILE%\.krew\bin
```

> Add it under **User variables → Path**. You do not need to add it under **System variables → Path**.

After adding the PATH, close the Command Prompt and open a **new** Command Prompt.

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
