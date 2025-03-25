# 御調子門 -AZAZEL system- : Tactical Delaying Action via the Cyber-Scapegoat Gateway

## **Abstract**  
Modern cyber threats are becoming increasingly automated and rapid, allowing attackers to breach systems in minimal time. Traditional honeypots focus on passive observation, and decoy servers aim to mislead attackers. However, neither provides an effective mechanism to delay adversaries’ progress, which is crucial for gaining time to deploy defensive measures.  

**"御調子門 -AZAZEL system-" is a portable security gateway that implements cyber deception techniques to delay attackers’ actions.** Built on a **Raspberry Pi 5 (8GB) hybrid architecture**, it utilizes **cyber-scapegoat deception**, where attacks are absorbed and manipulated rather than merely observed. The system integrates **real-time intrusion monitoring, network delay mechanisms, and adversary behavior fixation** using open-source software, ensuring **low-cost, high-efficiency cyber defense**.  

By leveraging **tactical delaying actions inspired by military land warfare**, this approach **controls and disrupts attackers while preserving valuable response time for defenders**. Unlike traditional deception systems, which focus solely on collecting attack data, **御調子門 actively manipulates the attack process to increase adversarial fatigue and decrease operational effectiveness**.  

This talk introduces the **architecture, practical implementation, and defensive advantages of a cyber-scapegoat gateway** and how it enhances active cyber defense in **hostile network environments such as public Wi-Fi or unverified infrastructures**.  

---

## **Description**  

### **1. Introduction**  
Modern cybersecurity defense must move beyond passive monitoring and immediate attack blocking. Attackers are increasingly using automated tools that quickly scan, exploit, and establish persistence within seconds. **Traditional honeypots collect attack data but do not interfere with or slow down adversaries. Decoy servers mislead attackers but do not impact their decision-making time.**  

This presentation introduces **御調子門 -AZAZEL system-**, a **portable, low-cost cyber deception gateway that incorporates tactical delaying actions** to provide an effective response against real-world cyber threats. **By leveraging the concept of cyber-scapegoating, the system not only misdirects attackers but actively slows them down using real-time intervention techniques.**  

Built on **Raspberry Pi 5 (8GB) with a hybrid architecture**,御調子門 employs:  
- **Real-time traffic manipulation** using `tc` (Traffic Control) and `iptables`  
- **Cyber-scapegoat deception** to absorb and delay attacks rather than just observing them  
- **Automated logging and threat classification** using Fluent Bit and MITRE ATT&CK  
- **Integration with public Wi-Fi and untrusted network environments**, ensuring adaptability for diverse deployment scenarios  

This talk will explore the **design, deployment, and defensive applications** of this **portable security gateway**, demonstrating its **effectiveness in delaying attacks while providing defenders with essential response time**.

---

### **2. Tactical Delaying Action in Cybersecurity**  
#### **2.1. Military Delaying Action: A Defensive Strategy**  
In military land warfare, **delaying actions** are used to **slow enemy forces, disrupt their movements, and create opportunities for counterattacks**. These tactics include:  
- **Strategic withdrawal while applying resistance** to force attackers into resource exhaustion  
- **Obstacle deployment to manipulate enemy pathways**  
- **Diversionary targets to redirect enemy focus**  

御調子門 applies these principles to cybersecurity by **deliberately controlling an attacker's progress, rather than merely blocking access**.

---

### **3. The Cyber-Scapegoat Model: Beyond Traditional Honeypots**  
📌 **Problem:** Previous deception techniques fail to **actively interfere with an attacker’s workflow**.  
📌 **Solution:** Cyber-scapegoats **absorb attacks and delay adversaries, increasing their operational fatigue**.  

| **Method** | **Honeypots** | **Decoy Servers** | **Cyber-Scapegoat (御調子門)** |
|-----------|--------------|------------------|----------------------------|
| **Purpose** | Collect attack data | Misdirect attackers | **Actively delay and disrupt attacks** |
| **Impact on Attackers** | No direct interaction | Passive deception | **Manipulates and slows adversaries** |
| **Operational Outcome** | Intelligence gathering | Temporary misdirection | **Fatigue attackers and buy defender response time** |

Unlike traditional deception models,御調子門 **exploits attacker persistence by prolonging their engagement with non-critical assets**.

---

### **4. Hybrid Architecture and Deployment**  
📌 **Challenge:** Running **active deception and tactical delay mechanisms** on resource-limited hardware.  
📌 **Solution:** A **hybrid system** that offloads deep attack analysis to an external laptop.  

#### **4.1. System Overview**  
📌 **御調子門 operates as a portable gateway, intercepting and delaying attacks before they reach critical assets.**  

🔹 **Key Components:**  
- **Raspberry Pi 5 (8GB) as the core gateway**  
- **Containerized OpenCanary for deception**  
- **Real-time network manipulation with `tc` and `iptables`**  
- **Automated log forwarding via Fluent Bit**  
- **External laptop for in-depth forensic analysis**  

🔹 **Deployment Use Cases:**  
- **Security for public Wi-Fi and travel networks**  
- **SOC (Security Operations Center) incident response augmentation**  
- **Cyberwarfare research and adversary behavior modeling**  

---

### **5. Implementation and Attack Mitigation Techniques**  
📌 **御調子門 actively intervenes in attack processes rather than just logging them.**  

#### **5.1. Network Delay & Redirection**  
📌 **Key Mechanism:** Slow down reconnaissance and exploit attempts using dynamic network manipulation.  

🔹 **Methods Used:**  
- **`tc` to artificially increase latency in suspicious connections**  
- **`iptables` rules to reroute attackers into deception environments**  
- **Adaptive response, progressively increasing delays on persistent threats**  

#### **5.2. Logging, Threat Classification, and MITRE ATT&CK Integration**  
📌 **Key Mechanism:** **Suricata intrusion alerts** processed via Fluent Bit and classified using MITRE ATT&CK.  

🔹 **How It Works:**  
- **Suricata detects unusual network activity.**  
- **Fluent Bit sends logs to an external laptop.**  
- **Kibana visualizes the attack timeline, mapped to MITRE ATT&CK.**  

---

### **6. Key Benefits and Tactical Advantages**  
📌 **御調子門 offers advantages beyond traditional deception techniques:**  

🔹 **Delaying attackers to increase defensive response time**  
🔹 **Cyber-scapegoat model actively manipulates adversary behavior**  
🔹 **Lightweight, portable deployment suitable for high-risk environments**  
🔹 **OSS-based, making it cost-effective and adaptable**  

---

📌 **御調子門 redefines cyber deception by integrating tactical delaying actions, enabling portable, low-cost active defense.**  
📌 **This talk showcases its architecture, real-world applications, and strategic advantages in cyber warfare scenarios.**  

## **目的**

- **未承認ネットワークやフリーWi-Fiに安全に接続するためのゲートウェイ**  
- **攻撃を検知し、ユーザーに通知しつつ、攻撃者を誘導して時間を稼ぐ（遅滞戦術）**  
- **アクティブサイバーディフェンスの一環として、攻撃者のリソースを消耗させる**  

## **設計思想**

- **攻殻機動隊の「身代わり防壁」に着想を得たサイバーデセプション技術**  
- **従来のハニーポットとは異なり、攻撃者を欺き、リソースを浪費させる「スケープゴート」戦術を採用**  
- **最終的に、攻撃を検出し、迎撃準備を整えるための時間を稼ぐ**  
- **Raspberry Piを採用し、低コスト・可搬性・省電力を優先**  
- **単体運用時はリアルタイム通知と遅滞戦術を実行し、接続端末があれば分析機能を追加**  

---

## **構成**

### **1. ハードウェア**

- **Raspberry Pi 4（SSDブート）**
  - **モバイル型 Intrusion Countermeasure Electronics（ICE）として運用**
  - 省電力かつ可搬性を重視し、フィールド運用が可能  

### **2. ネットワーク監視**

- **Suricata（IDSモード）**
  - パケット監視による攻撃検知  
  - 侵入の兆候を素早く検出し、通知  
  - **IPSモードは使用せず、あくまで検知とログ取得に特化**  

### **3. 攻撃通知**

- **Mattermost によるリアルタイム通知**
  - 侵入や攻撃が発生した際に即時通知  
  - **攻撃の種類を分類し、通知の優先度を設定**（例：DDoS、ポートスキャン、既知のエクスプロイト攻撃）  

### **4. デセプション技術**

- **OpenCanary によるデコイ戦術**
  - **攻撃者を意図的に脆弱な環境に誘導し、リソースを浪費させる**
  - **通常のハニーポットとしての分析ではなく、攻撃を受けるための「囮」として利用**
  - **具体的な誘導手法**
    - 攻撃者が興味を持ちやすいサービス（SSH, SMB, HTTP, MySQL など）をエミュレート  
    - 偽の脆弱なアプリケーションをホスト  
    - **「攻撃成功」と誤認させた後、意図的に長時間の応答遅延を発生させることで時間を浪費**  

### **5. ログ収集と可視化**

- **単体運用時**
  - ログの集約は行わず、リアルタイムで通知と遅滞戦術を優先  
- **ラップトップ接続時**
  - **軽量な可視化ツール（Grafana, Kibana などのシンプル構成）で分析**  
  - **リアルタイムストリーミングではなく、バッチ処理でログを転送**  

---

## **戦術的要素**

### **1. 遅滞戦術（戦術的遅滞行動）**

- **攻撃者をデコイに誘導し、無駄な攻撃を継続させることで時間を稼ぐ**
- **最終的に迎撃可能な状況を作る（法執行・物理的対抗策を想定）**

### **2. 攻撃者のリソース消耗**

- **攻撃を仕掛けた際、意図的に処理を遅延させ、攻撃者のCPU・ネットワーク帯域を浪費させる**
- **特定の攻撃を行った際に意図的な無限ループやタイムアウトを発生させる**

### **3. フェイク環境の構築**

- **「攻略しやすい」と思わせる環境を模倣し、攻撃者を惹きつける**
- **実際のシステムとは異なる挙動を示し、攻撃者に誤情報を提供**

---

## **導入シナリオ**

1. **未承認ネットワーク（例：カフェ、ホテルWi-Fi）に接続する際のゲートウェイ**
   - VPNを通さずに直接ネットワークへアクセスすることを防止  
   - 不審なトラフィックを監視し、攻撃が発生した場合に即座に通知  

2. **企業や自治体の小規模SOC/NOCとしての活用**
   - 小規模環境向けに、攻撃監視機能を提供  
   - IDS/IPS機能を備えた簡易的なセキュリティソリューションとして利用可能  

3. **フィールドオペレーション（特殊部隊・捜査機関向け）**
   - **敵対勢力のサイバー攻撃を事前に検知し、遅延戦術で時間を稼ぐ**
   - 攻撃者の挙動を分析し、最適な迎撃タイミングを確保  

---

## **まとめ**

御調子門 -AZAZEL system- は、単なる監視ゲートウェイではなく、攻撃者を欺き、リソースを消耗させ、迎撃可能な時間を稼ぐ **「サイバースケープゴート」** である。  
従来の防御的なハニーポットとは異なり、攻撃を積極的に引き受けることで **「敵の作戦行動時間を削減し、防御側に有利な状況を作る」** ことを目的とする。  
この仕組みを **Raspberry Pi 4上で構築し、低コストかつ可搬性の高いサイバーデセプションデバイスとして運用** する。  
