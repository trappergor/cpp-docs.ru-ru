---
title: "Функции обмена данными полями записей | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO (объекты доступа к данным), обмен полями записей (DFX)"
  - "ODBC, функции массового обмена данными RFX"
  - "RFX (обмен полями записей), классы ODBC"
  - "DFX (обмен полями записей DAO) функции обмена данными"
  - "функции DFX"
  - "блочные функции RFX"
  - "обмен полями записей DAO (DFX)"
  - "RFX (обмен полями записей), классы DAO"
  - "ODBC, RFX"
  - "RFX (обмен полями записей), функции обмена данными"
  - "обмен полями записей (RFX)"
ms.assetid: 6e4c5c1c-acb7-4c18-bf51-bf7959a696cd
caps.latest.revision: 13
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функции обмена данными полями записей
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом разделе перечислены функции обмена полями записей \([RFX](#_mfc_rfx_functions_.28.odbc.29), [Bulk RFX](#_mfc_bulk_rfx_functions_.28.odbc.29) и [DFX](#_mfc_dfx_functions_.28.dao.29)\), используемые для автоматизации передачи данных между объектом набора записей и источником данных и выполнения других операций с данными.  
  
 При использовании классов на основе ODBC и реализации массовой выборки строк необходимо вручную переопределить функцию\-член `DoBulkFieldExchange``CRecordset` путем вызова функций Bulk RFX для каждого элемента данных, соответствующего столбцу источника данных.  
  
 Если в классах на основе ODBC массовая выборка строк не реализована или если вы используете классы на основе DAO, мастер ClassWizard переопределит функцию\-член `DoFieldExchange``CRecordset` или `CDaoRecordset` путем вызова функций RFX \(для классов ODBC\) или функций DFX \(для классов DAO\) для каждого элемента данных поля в наборе записей.  
  
 Функции обмена полями записей передают данные каждый раз, когда платформа вызывает `DoFieldExchange` или `DoBulkFieldExchange`. Каждая функция передает определенный тип данных.  
  
 Дополнительные сведения об использовании этих функций см. в статьях [Обмен полями записей: принцип работы RFX \(ODBC\)](../../data/odbc/record-field-exchange-how-rfx-works.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md).  
  
 Для столбцов данных с динамической привязкой можно самостоятельно вызвать функции RFX и DFX, как описано в статьях [Набор записей. Динамическая привязка столбцов данных \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md). Кроме того, можно написать собственные подпрограммы RFX и DFX, как описано в техническом примечании [43](../Topic/TN043:%20RFX%20Routines.md) \(для ODBC\) и техническом примечании [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) \(для DAO\).  
  
 Пример функций RFX и Bulk RFX в функциях `DoFieldExchange` и `DoBulkFieldExchange` см. в разделах [RFX\_Text](../Topic/RFX_Text.md) и [RFX\_Text\_Bulk](../Topic/RFX_Text_Bulk.md). Функции DFX очень похожи на функции RFX.  
  
### Функции RFX \(ODBC\)  
  
|||  
|-|-|  
|[RFX\_Binary](../Topic/RFX_Binary.md)|Передает массивы байтов типа [CByteArray](../../mfc/reference/cbytearray-class.md).|  
|[RFX\_Bool](../Topic/RFX_Bool.md)|Передает логический тип данных.|  
|[RFX\_Byte](../Topic/RFX_Byte.md)|Передает один байт данных.|  
|[RFX\_Date](../Topic/RFX_Date.md)|Передает значения времени и даты с помощью [CTime](../Topic/CTime%20Class.md) или **TIMESTAMP\_STRUCT**.|  
|[RFX\_Double](../Topic/RFX_Double.md)|Передает данные двойной точности с плавающей запятой.|  
|[RFX\_Int](../Topic/RFX_Int.md)|Передает целочисленные данные.|  
|[RFX\_Long](../Topic/RFX_Long.md)|Передает длинные целые данные.|  
|[RFX\_LongBinary](../Topic/RFX_LongBinary.md)|Передает данные больших двоичных объектов \(BLOB\) с объектом класса [CLongBinary](../../mfc/reference/clongbinary-class.md).|  
|[RFX\_Single](../Topic/RFX_Single.md)|Передает данные с плавающей запятой.|  
|[RFX\_Text](../Topic/RFX_Text.md)|Передает строковые данные.|  
  
### Функции Bulk RFX \(ODBC\)  
  
|||  
|-|-|  
|[RFX\_Binary\_Bulk](../Topic/RFX_Binary_Bulk.md)|Передает массивы байтов данных.|  
|[RFX\_Bool\_Bulk](../Topic/RFX_Bool_Bulk.md)|Передает массивы логических данных.|  
|[RFX\_Byte\_Bulk](../Topic/RFX_Byte_Bulk.md)|Передает массивы отдельных байтов.|  
|[RFX\_Date\_Bulk](../Topic/RFX_Date_Bulk.md)|Передает массивы данных типа **TIMESTAMP\_STRUCT**.|  
|[RFX\_Double\_Bulk](../Topic/RFX_Double_Bulk.md)|Передает массивы данных двойной точности с плавающей запятой.|  
|[RFX\_Int\_Bulk](../Topic/RFX_Int_Bulk.md)|Передает массивы целочисленных данных.|  
|[RFX\_Long\_Bulk](../Topic/RFX_Long_Bulk.md)|Передает массивы длинных целых данных.|  
|[RFX\_Single\_Bulk](../Topic/RFX_Single_Bulk.md)|Передает массивы данных с плавающей запятой.|  
|[RFX\_Text\_Bulk](../Topic/RFX_Text_Bulk.md)|Передает массивы данных типа **LPSTR**.|  
  
### Функции DFX \(DAO\)  
  
|||  
|-|-|  
|[DFX\_Binary](../Topic/DFX_Binary.md)|Передает массивы байтов типа [CByteArray](../../mfc/reference/cbytearray-class.md).|  
|[DFX\_Bool](../Topic/DFX_Bool.md)|Передает логический тип данных.|  
|[DFX\_Byte](../Topic/DFX_Byte.md)|Передает один байт данных.|  
|[DFX\_Currency](../Topic/DFX_Currency.md)|Передает данные денежных единиц типа [COleCurrency](../Topic/COleCurrency%20Class.md).|  
|[DFX\_DateTime](../Topic/DFX_DateTime.md)|Передает данные даты и времени типа [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md).|  
|[DFX\_Double](../Topic/DFX_Double.md)|Передает данные двойной точности с плавающей запятой.|  
|[DFX\_Long](../Topic/DFX_Long.md)|Передает длинные целые данные.|  
|[DFX\_LongBinary](../Topic/DFX_LongBinary.md)|Передает данные больших двоичных объектов \(BLOB\) с объектом класса `CLongBinary`. Для DAO рекомендуется использовать [DFX\_Binary](../Topic/DFX_Binary.md).|  
|[DFX\_Short](../Topic/DFX_Short.md)|Передает короткие целые данные.|  
|[DFX\_Single](../Topic/DFX_Single.md)|Передает данные с плавающей запятой.|  
|[DFX\_Text](../Topic/DFX_Text.md)|Передает строковые данные.|  
  
## См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)   
 [CRecordset::DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)   
 [CRecordset::DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md)   
 [CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md)