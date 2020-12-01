## 1. 收貨資料ETL(Extract-Transform-Load) :id=etl

- 接收工廠收貨資料

> 1. 資料接收公司廠別清單<br>
> 2. 收貨年月 = 上個月(排程執行年月 - 1個月)

## 2.MAT_WEIGHT_CHK(單重異常資料) :id=chkWeight

- CLAUSE ->單重為0 OR null為異常

## 3.[DFD]收貨單接收 diagram(Legacy) :id=recAccp

```mermaid
graph TD;
id[行政中心]
id2((接收各行政中心資料<br>PRO_DATA_TRANSFER排程))
id3[收貨資料暫存檔<br>MAT_TMP_ACCPD]
id4((海外資料寫入收貨明細檔))
id5((台灣資料寫入收貨明細檔))
id6[收貨明細檔<br>MAT_ACCPD]
id7((檢查原物料單重資料))
id8((收貨異常資料<br>MAT_WEIGHT_CHK))
id--收貨資訊-->id2
id2--海外收貨資料-->id3
id3--海外收貨資料-->id4
id4--海外收貨資訊-->id6
id2--TW收貨資訊-->id5
id5--TW收貨資訊-->id6
id6--收貨資訊-->id7
id7--單重異常資訊-->id8
```

## 4.[DFD]收貨單接收-2019改版 diagram AS-IS :id=flow

```mermaid
graph TD;
id[物編系統]
id2[自編物料ERP]
id3[各區行政中心]
id4((invoke BD_GSCM_ACCP<br>寫入收貨單<br>8th 20:00))
id5[收貨資料暫存檔<br>MAT_TMP_ACCPD]
Job(PRO_DATA_TRANSFER)
id6((1.海外資料寫到收貨明細檔<br>PRO_MAT_ACCPD_OVER))
id7[收貨明細檔<br>MAT_ACCPD]
id8((2.台灣資料寫到收貨明細檔<br>PRO_MAT_ACCPD))
id9((檢查原物料單重資料))
id10[收貨異常資料<br>MAT_WEIGHT_CHK]
id-->id3
id2-->id3
id3-->id4
id4-->id5
id5-->Job
Job-->id6
Job-->id8
id6--海外-->id7
id8--TW-->id7
id7--收貨資訊-->id9
id9--單種異常資訊-->id10
```

## 5.BD_GSCM_ACCP :id=crongscmaccp

- 取各區行政中心(AIS)收貨單寫入資材分析

```sql
select * from MAT_SYSCODE where sys_keyname ='BD_GSCM_ACCP_DB';
```

- SYS_DATA8-運行MK(Y/N)
- SYS_DATA9-廠別(J8; J8,V2; %(default))

## 6.ETL(`Extract-Transform-Load`) :id=source

### 6.1 DataSource(`EXTRACT`)

> VIE_GSCM_ACCPD(各區收貨資料檔)

### 6.2 Data_Dist(`TRANSFORM`)
> MAT_TMP_ACCP(收貨資料暫存檔)

### 6.3 Data_accp(`LOAD`)
> MAT_ACCPD(收貨資料檔)

## 7.各區行政中心(AIS)條件 :id=ais

### 7.1 FUN_DATA_TRANSFER_PYC[2019/06/17]刪除

- 僅保留台灣區收貨資料條件，其餘刪除

### 7.1.2 例外處理
> 台灣區收貨資料條件: ADT.VIE_FINANCE_ACCEPTM@LUXPCCDB(台灣AIS) 固定地區別為
V003 平政[ESB上線後，保留]
- 公司別(P65,P33)

### 7.2 FUN_DATA_TRANSFER_CHINA 

- 僅保留廠別724,TW區收貨條件

### 7.2.2 例外處理
>3.2.例外處理-廠別724由TW區收收貨資料-來源: ADT.VIE_FINANCE_ACCEPTM@LUXPCCDB (台灣AIS)
地區別歸為C008 黃江
- 公司別('P20','P33')

### 7.3 FUN_DATA_TRANSFER_BDPH
- BDPH廠，ESB 上線後，後續考慮需刪除]

### 7.4 FUN_DATA_TRANSFER_ID(印尼區)
- 印尼區-ESB上線後，後續需考慮刪除]

