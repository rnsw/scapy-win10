# scapy-win10
win10 python27  scapy 
1. 安装 pip install scapy==2.3.3
2. 安装 VCForPython27.msi , WinPcap_4_1_2.exe，
3. 解压 WpdPack_4_1_2.zip 将 Include ,Lib  复制到 python 安装目录下的 Include 和 libs 中
4. 安装  
pcap-1.1.win32-py2.7.exe    
dnet-1.12.win32-py2.7.exe   
Win10Pcap-v10.2-5002.msi   
impacket-0.9.11.win32.msi   


错误1
global name 'log_runtime' is not defined

修改文件
C:\Python27\Lib\site-packages\scapy\arch\windows\compatibility.py

将
from scapy.arch.consts import LOOPBACK_NAME 
from scapy.config import conf,ConfClass  
改为
from scapy.arch.consts import LOOPBACK_NAME 
from scapy.config import conf,ConfClass 
from scapy.arch.pcapdnet import PcapTimeoutElapsed      #PcapTimeoutElapsed 
from scapy import plist                                  #plist 
from scapy.all import log_runtime, MTU, ETH_P_ALL          #log_runtime, MTU, ETH_P_ALL 
