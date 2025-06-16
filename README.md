# 🌐 基本網路架構圖

以下為一個典型的企業網路基礎架構，區分為外部網路（Internet）、DMZ 區域（半信任區）與內部網路（信任區）：

---

## 📊 架構圖（Mermaid）

```mermaid
graph TB
    subgraph Internet
        A[使用者裝置<br/>(Browser/Client)]
    end

    subgraph DMZ（半信任區）
        B[防火牆 Firewall]
        C[反向代理 / 負載平衡器<br/>(Nginx / ELB)]
        D[Web 應用伺服器<br/>(App Server)]
    end

    subgraph Internal Network（內部區域）
        E[資料庫伺服器<br/>(DB Server)]
        F[內部服務（AD, DNS, Mail）]
        G[監控系統（Zabbix / Prometheus）]
    end

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> G

