---
title: "CFieldExchange Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFieldExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFieldExchange class"
  - "типы данных [C++], пользовательский"
  - "enum FieldType"
  - "enum FieldType, CFieldExchange"
  - "FieldType enumeration"
  - "RFX (record field exchange) [C++]"
  - "RFX (record field exchange) [C++], classes for"
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
caps.latest.revision: 24
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFieldExchange Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Поддерживает запись обмен полями записей \(RFX\) и подпрограммы обмена полями записей \(bulk RFX\), используемые базой данных классифицируют.  
  
## Синтаксис  
  
```  
  
class CFieldExchange  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFieldExchange::IsFieldType](../Topic/CFieldExchange::IsFieldType.md)|Возвращает ненулевое значение, если текущая операция подходит для типа обновляемой поля.|  
|[CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md)|Не укажет тип элемента данных набора записей — столбец или параметр — представленный всех последующих вызовах RFX до следующего вызова функции `SetFieldType`.|  
  
## Заметки  
 `CFieldExchange` не имеет базовый класс.  
  
 Этот класс используется при написании процедуры обмена данными для пользовательских типов данных или реализуйте пакетная выборка строк; в противном случае не будете использовать этот класс.  RFX и групповой RFX обмен данными между элементами данных полей объекта набора записей и соответствующие поля текущей записи в источнике данных.  
  
> [!NOTE]
>  При работе с DAO \(DAO\) классифицируете, а не классов ODBC \(ODBC\) использует класс [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md).  Дополнительные сведения см. в статье [Общие сведения: программирование базы данных](../../data/data-access-programming-mfc-atl.md).  
  
 Объект `CFieldExchange` предоставляет контекстные сведения, необходимые для обмена полей записей или обмена полей записей, чтобы помнить.  Объекты `CFieldExchange` поддерживают несколько операций, включая параметры привязки и элементы данных полей и флаги параметров различные в полях текущей записи.  RFX и массовых операций RFX, выполняемые на элементах данных установлен записей\- класса `enum`**FieldType** типов, определенных в `CFieldExchange`.  Возможные значения **FieldType**:  
  
-   **CFieldExchange::outputColumn** для элементов данных полей.  
  
-   **CFieldExchange::inputParam** или **CFieldExchange::param** для элементов данных входного параметра.  
  
-   **CFieldExchange::outputParam** для элементов данных параметров вывода.  
  
-   **CFieldExchange::inoutParam** для элементов данных параметров ввода\-вывода.  
  
 Большая часть функций элементов и элементов данных типа предоставляется для написания собственных пользовательских функций RFX подпрограммы.  Необходимо использовать `SetFieldType` часто.  Дополнительные сведения см. в разделе статьи [Обмен полями записей \(RFX\)](../../data/odbc/record-field-exchange-rfx.md) и [набор записей \(ODBC\)](../../data/odbc/recordset-odbc.md).  Дополнительные сведения о массовой строке выборке см. в статье [Набор записей. Пакетная выборка строк \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md).  Дополнительные сведения о функциях RFX и bulk RFX глобальных см. в разделе [Функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md) в разделе макросов и глобальных MFC этой ссылки.  
  
## Иерархия наследования  
 `CFieldExchange`  
  
## Требования  
 **Header:**  afxdb.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../Topic/CRecordset%20Class.md)