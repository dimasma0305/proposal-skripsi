# Chapter 4 Database Tables

## 表4-1 SuspicionEvent表

| 字段名 | 类型 | 主键 | 允许空 | 说明 |
| --- | --- | --- | --- | --- |
| Id | int | 是 | false | Primary key |
| ParticipationId | int | 否 | false | FK ke Participation |
| Type | string | 否 | false | Kode aturan (StolenFlag, dst.) |
| ScoreDelta | int | 否 | false | Bobot yang ditambahkan |
| Details | string | 否 | false | Deskripsi bukti |
| TimeUtc | DateTimeOffset | 否 | false | Waktu kejadian |
| GameId | int | 否 | false | FK ke Game |
| RelatedParticipationId | int | 否 | true | Partisipasi terkait (opsional) |

## 表4-2 SuspicionRule表

| 字段名 | 类型 | 主键 | 允许空 | 说明 |
| --- | --- | --- | --- | --- |
| RuleCode | string | 是 | false | Kode aturan unik |
| Weight | int | 否 | false | Bobot risiko |
| Description | string | 否 | false | Keterangan aturan |

## 表4-3 Participation表

| 字段名 | 类型 | 主键 | 允许空 | 说明 |
| --- | --- | --- | --- | --- |
| Id | int | 是 | false | Primary key |
| SuspicionScore | int | 否 | false | Akumulasi skor risiko (mentah, tak ternormalisasi) |
| Status | ParticipationStatus | 否 | false | Status kepesertaan |
