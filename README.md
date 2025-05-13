# ⛏️ Tutorial: Mine Pepe3 Blocks on Microsoft Windows

Follow these steps to mine blocks using the official Pepe3 Windows wallet.

---

### 🛠️ Instructions (All-in-One)

1. **Download the Wallet:**

   Download `pepe3-qt-windows.zip` from the official release page or provided link.

2. **Extract the ZIP File:**

   Use File Explorer to navigate to your Downloads folder and extract `pepe3-qt-windows.zip`.

3. **Create Configuration File:**

   - Press `Win + R` to open the **Run** dialog.
   - Type `notepad` and press **OK**.
   - Paste the following into Notepad:

     ```ini
     rpcuser=rpc_pepe3
     rpcpassword=dR2oBQ3K1zYMZQtJFZeAerhWxaJ5Lqeq9J2
     rpcbind=127.0.0.1
     rpcallowip=127.0.0.1
     listen=1
     server=1
     addnode=node3.walletbuilders.com
     ```

   - Go to `File → Save As...`
   - Set **Save as type** to: `All Files (*.*)`
   - Name the file: `pepe3.conf`
   - In the path bar, type `%appdata%` and press **Enter**
   - Create a new folder named `Pepe3` and save the file inside it.

4. **Create Mining Script:**

   - Open a new Notepad window (`Ctrl + N`)
   - Paste the following:

     ```bat
     @echo off
     set SCRIPT_PATH=%cd%
     cd %SCRIPT_PATH%
     echo Press [CTRL+C] to stop mining.
     :begin
     for /f %%i in ('pepe3-cli.exe getnewaddress') do set WALLET_ADDRESS=%%i
     pepe3-cli.exe generatetoaddress 1 %WALLET_ADDRESS%
     goto begin
     ```

   - Save as `mine.bat` in the same folder where you extracted the `.zip` file.
   - Set **Save as type** to: `All Files (*.*)`

5. **Start Mining:**

   - Run the wallet (`pepe3-qt.exe`)
   - Once loaded, double-click `mine.bat` to start mining blocks.

---

🎉 You are now mining Pepe3 blocks on Windows!
