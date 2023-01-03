# Container 介紹
    若要了解Container帶來的好處，就要先了解Container的歷史演進

## 過去如何部署apps?

1. 部署在特定的Server上
    - 自行準備硬體設施、作業系統、網路連結、軟體相關套件、apps本身程式碼
    - 如果需要更多的運算資源，多加幾台電腦
    - 問題：**花費時間與精力，通常部署可能會花到幾個月且無法難以利用與維護**

2. Virtual Machine(VM)
    - 虛擬化技術則可以使單一的實體電腦能執行不同的虛擬伺服器與作業系統
    - Hypervisor：用以允許不同的VM共享同樣的硬體
    - 採用虛擬化技術讓我們 **花費更少時間部署，且更容易複製，因為VM可以被映像化**
    - 問題：**然而該app的所有相依套件仍然綁在一起，並且不太容易從一台虛擬機器或一個hypervisor的產品遷移到另外一個**
    - 問題：**如果在該VM上運行許多的app，這些app共有的相依套件並沒有被分隔開來，在更新或版本上會彼此影響**
    - VM-Centric ways：或許可以透過一個app有個專門的VM來執行，但在Scalability上非常沒有效率，以kernel的更新來講，專門的VM變便得難以維護且浪費時間資源

3. Container
    - Container 透過將User spaces分離出來，只用以執行app的程式
    - Container 不像VM裝了整個的作業系統，且不用重啟整個作業系統來BOOT UP VM

![container_img](../imgs/container_involving.png)


