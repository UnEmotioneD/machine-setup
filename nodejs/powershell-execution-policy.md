# PowerShell Execution Policy

Fix the `npm` command not working on **Windows PowerShell**.

---

## Check Current Policy

Open `PowerShell` or `cmd` with **Admin Privilege**.

```sh
Get-ExecutionPolicy
```

Output would be `Restricted`.

## Allow for Current User

```sh
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

Enter `Y`.

## Check Functionality

Now `npm` commands should work.

```sh
npm --version
```
