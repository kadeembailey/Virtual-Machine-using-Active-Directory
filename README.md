# 🖥️ How to Create a Virtual Machine with Active Directory

This tutorial walks you through the step-by-step process of creating a virtual machine and configuring it with Active Directory Domain Services (AD DS) using Windows Server.

---

## 🧰 Tools Used

- Virtualization Software (e.g., Hyper-V, VMware, or VirtualBox)
- Windows Server 2019 ISO
- Windows 10 ISO (optional, for client testing)
- Active Directory Domain Services (AD DS)

---

## 📦 Step 1: Create a New Virtual Machine

1. Launch your virtualization software.
2. Click on **"New Virtual Machine"**.
3. Name the VM and select **Generation 2** (if using Hyper-V).
4. Assign at least **2GB of RAM**.
5. Create a **new virtual hard disk (VHDX)** of 60 GB or more.
6. Attach the **Windows Server ISO**.

![Create VM](images/create-vm.png)

---

## 💿 Step 2: Install Windows Server

1. Start the virtual machine.
2. Boot from the ISO and begin the installation process.
3. Choose "Windows Server 2019 Standard (Desktop Experience)".
4. Complete the installation and create an admin password.

![Install Windows](images/install-windows.png)

---

## 🧱 Step 3: Install Active Directory Domain Services (AD DS)

1. Open **Server Manager**.
2. Click **"Add Roles and Features"**.
3. Select **Role-based or feature-based installation**.
4. Choose your server.
5. Select **Active Directory Domain Services**.
6. Click **Next** through the wizard and install.

![Install AD DS](images/install-ad-ds.png)

---

## 🛡️ Step 4: Promote Server to Domain Controller

1. In Server Manager, click the flag notification → **Promote this server to a domain controller**.
2. Choose **"Add a new forest"** and enter a **root domain name** (e.g., `corp.local`).
3. Set a **Directory Services Restore Mode (DSRM)** password.
4. Accept defaults and complete the wizard.
5. The server will **restart automatically**.

![Promote to DC](images/promote-dc.png)

---

## 🧪 Step 5: Test Active Directory

1. Log back into the domain controller.
2. Open **Active Directory Users and Computers** from Server Manager > Tools.
3. You should see your new domain (e.g., `corp.local`).
4. Optionally, join another VM to the domain to test connectivity.

![AD Test](images/ad-users-computers.png)

---

## 🗂️ File Structure of This Tutorial

```
vm-ad-tutorial/
├── README.md
└── images/
    ├── create-vm.png
    ├── install-windows.png
    ├── install-ad-ds.png
    ├── promote-dc.png
    └── ad-users-computers.png
```

---

## ✅ Final Notes

- Make sure virtualization is enabled in BIOS.
- Use a static IP address for your domain controller.
- Always take snapshots/checkpoints before major changes.

If you found this helpful, feel free to ⭐️ star the repo or open an issue for questions!
