組員:B0942210石宸緯

# X-server
# 原理
X Server 是控制本機端輸出與輸入設備的程式，負責螢幕上圖形之顯示，並驅動滑鼠及鍵盤等輸入設備，讓使用者可以透過這些輸入輸出介面，達到與應用軟體式互動的目的。
在家裡或小辦公室環境中，通常 X server 跟 X client 都是在同一台電腦上執行的。 然而也可以在效能較差的桌機上執行 X server，而將應用軟體安裝在效能比較強、比較貴的遠端伺服器上並執行 X 程式 (client) 來做事情。 在這種場景下，X client 與 server 之間的溝通就需透過網路來進行。
由於 Windows 作業系統上並沒有提供預設的 X server，如有需要使用者必須自行下載安裝。目前 Windows 作業系統上常見的 X server 軟體有以下幾個：
Hummingbird Exceed
X-win32
Xming 
MobaXterm
VcXsrv(這次專題使用)
# 安裝方式
設定使用WSL2為預設使用版本

    wsl --set-default-version 2
    
    
    
需要去控制台—>程式和功能—>開啟或關Windows功能–>勾選Windows子系統Linux版與虛擬機器平台

![image](https://user-images.githubusercontent.com/106713894/175457778-88ab5809-b754-4bdb-8d64-b5925f790a85.png)


下載X server連線工具，使用VcXsrv

https://sourceforge.net/projects/vcxsrv/

# 桌面配置

執行安裝 X Server 套件

        sudo apt-get install x11-apps


建立一個.bash_login並輸入以下內容

        # For WSL2
        export DISPLAY=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0.0
        export LIBGL_ALWAYS_INDIRECT=1
        
![image](https://user-images.githubusercontent.com/106713894/175459180-2d077231-2e87-4a19-bb2c-ada58adaeff4.png)

# 執行安裝 xfce4 桌面
        sudo apt-get install xfce4-terminal
        sudo apt-get install xfce4
![image](https://user-images.githubusercontent.com/106713894/175459494-411e932c-97e5-476b-b45a-277b33b1a219.png)

Display number 設置為0


跑完出現以下視窗即可

![image](https://user-images.githubusercontent.com/106713894/175459654-dc24c4f5-f9f6-42d3-bbe4-2ce7748896f3.png)

在Ubuntu 20.04 LTS終端機啟動X Server，輸入指令
        
        startxfce4
        
 ![image](https://user-images.githubusercontent.com/106713894/175459798-44c6930a-25c8-49ae-b32d-ad1faa18e9be.png)


出現此畫面即完成

![image](https://user-images.githubusercontent.com/106713894/175460022-aa8d8423-de20-4f4f-a8c9-9ab52bbc5958.png)


# 參考資料

https://ossf.denny.one/en/foss-programs/9265-xserver.html

https://blog.xuite.net/rockmansyz/twblog/115534608-Ubuntu++Server+%E5%AE%89%E8%A3%9D+Gnome+X-Windows+%E7%9A%84%E6%96%B9%E6%B3%95

https://zoomadmin.com/HowToInstall/UbuntuPackage/x-window-system
