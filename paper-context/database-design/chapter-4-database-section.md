## 第四章数据库设计草稿片段

### 数据库概念结构设计

根据系统功能需求，数据库概念结构围绕核心业务对象展开。总E-R图用于展示实体之间的主要关系，单实体E-R图用于展示每个实体的完整属性，避免总图因字段过多而拥挤。

系统总体E-R图见图4-2。

SuspicionEvent实体用于Log satu peristiwa anomali (jenis, bobot, waktu, detail) per partisipasi，其单实体E-R图见图4-3。
SuspicionRule实体用于Definisi aturan deteksi dan bobot penalti (dapat dikonfigurasi)，其单实体E-R图见图4-4。
Participation实体用于Partisipasi tim pada suatu game; menyimpan skor kecurigaan kumulatif，其单实体E-R图见图4-5。

### 数据库表设计

SuspicionEvent表用于Log satu peristiwa anomali (jenis, bobot, waktu, detail) per partisipasi，字段设计见表4-1。
SuspicionRule表用于Definisi aturan deteksi dan bobot penalti (dapat dikonfigurasi)，字段设计见表4-2。
Participation表用于Partisipasi tim pada suatu game; menyimpan skor kecurigaan kumulatif，字段设计见表4-3。

实体关系说明如下：
- Participation memiliki banyak SuspicionEvent：Participation 与 SuspicionEvent 之间为 1:m 关系。
- SuspicionEvent merujuk SuspicionRule via kode：SuspicionEvent 与 SuspicionRule 之间为 m:1 关系。
