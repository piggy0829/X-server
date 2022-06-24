組員:B0942210石宸緯

# X-server
X Server 是控制本機端輸出與輸入設備的程式，負責螢幕上圖形之顯示，並驅動滑鼠及鍵盤等輸入設備，讓使用者可以透過這些輸入輸出介面，達到與應用軟體式互動的目的。
在家裡或小辦公室環境中，通常 X server 跟 X client 都是在同一台電腦上執行的。 然而也可以在效能較差的桌機上執行 X server，而將應用軟體安裝在效能比較強、比較貴的遠端伺服器上並執行 X 程式 (client) 來做事情。 在這種場景下，X client 與 server 之間的溝通就需透過網路來進行。
由於 Windows 作業系統上並沒有提供預設的 X server，如有需要使用者必須自行下載安裝。目前 Windows 作業系統上常見的 X server 軟體有以下幾個：
Hummingbird Exceed
X-win32
Xming 
MobaXterm
VcXsrv(這次專題使用)
#安裝方式
