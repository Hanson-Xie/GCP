# GCP Cloud Architect Case Study

## Case company - Cymbal Direct

### Overview
1. Cymbal Direct 是一家網路B2C成衣與鞋業公司，訴求公平交易與永續，與棉花農夫合作並再投資他們的社區也是Cymbal Direct吸引年輕族群的原因。

### Solution concept
1. Delivery by Drone使具有證照的無人機玩家可以與Cymbal Direct組隊來運送該公司鞋子，達成更好的運輸效率。無人機同時也有串流影像連結至無人機玩家與消費者，使得消費者可以在地圖上看到他們購買的產品
2. Cymbal Direct想要發行一個正式的API給合作對象，API會採用版本控制與規模控制的方式，並使使用者可以追蹤、加密與得利於此
3. 一個社群整合性的服務：用Machine learning 過濾所有有hashtag Cymbal Direct 的產品照片，確保照片是合適的

### Existing environnment
1. Delivery by Drone
    - Kubernetes: 網站前端、無人機駕駛與貨運管理系統
    - MongoDB clusters: 無人機定位資訊與卡車地點
    - Virtual Machines: 無人機串流語音 (stateful connection)
2. Purchase & Product APIs
    - API 目前只有被單純的放入一個apps的大區塊，尚未開發合作夥伴整合，也沒有版本控制
    - Running on Ubuntu Linux VMs
    - API 沒有內建權限控制
3. Social Media Highlighting
    - Single SuSE linux VM
    - MYSQL DB
    - Redis
    - Python

### Business requirements
1. 當擴張到測試市場時，規模可以隨之改變
2. 精簡開發
3. 盡可能將開發者的時間花在核心業務
4. 盡量讓合作夥伴透過api下單
5. 發展社群媒體highlight服務並確保恰當內容

### Technical requirements
1. Managed services
2. Container-based workload
3. Highly scalable environment
4. Standardization where possible
5. Existing virtualization infrastructure refactored over time
6. Secure partner integration
7. Streaming IoT data


