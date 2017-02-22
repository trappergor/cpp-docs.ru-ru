---
title: "CDaoFieldExchange Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoFieldExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoFieldExchange class"
  - "доступ к данным DAO.NET, record field exchange (DFX)"
  - "обмен полями записей DAO (DFX)"
  - "обмен полями записей DAO (DFX), DAO Record Field Exchange"
  - "exchanging data between databases and recordsets"
  - "field exchange"
  - "field exchange, record for DAO classes"
  - "обмен полями записей (RFX)"
  - "обмен полями записей (RFX), DAO - классы"
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDaoFieldExchange Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Поддерживает подпрограммы обмена полями записей \(DFX DAO\), используемые классами баз данных DAO.  
  
## Синтаксис  
  
```  
class CDaoFieldExchange  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoFieldExchange::IsValidOperation](../Topic/CDaoFieldExchange::IsValidOperation.md)|Возвращает ненулевое значение, если текущая операция подходит для типа обновляемой поля.|  
|[CDaoFieldExchange::SetFieldType](../Topic/CDaoFieldExchange::SetFieldType.md)|Не укажет тип элемента данных набора записей — столбец или параметр — представленный всеми последующими вызовами метода DFX действует до следующего вызова `SetFieldType`.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoFieldExchange::m\_nOperation](../Topic/CDaoFieldExchange::m_nOperation.md)|Операция, выполняемая DFX текущим вызовом к функции\-члену `DoFieldExchange` набора записей.|  
|[CDaoFieldExchange::m\_prs](../Topic/CDaoFieldExchange::m_prs.md)|Указатель к набору записей, на котором выполняются операции DFX.|  
  
## Заметки  
 `CDaoFieldExchange` не имеет базовый класс.  
  
 Этот класс используется при написании процедуры обмена данными для пользовательских типов данных; в противном случае не будете использовать этот класс.  DFX обмен данными между элементами данных полей объекта [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) и соответствующие поля текущей записи в источнике данных.  DFX управляет обменом в обоих направлениях, из источника данных и к источнику данных.  См. раздел [Техническая примечание 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) дополнительные сведения о записи пользовательских подпрограммах DFX.  
  
> [!NOTE]
>  Классы баз данных DAO MFC отличаются от классов баз данных на основе ODBC \(ODBC\).  Все имена классов базы данных DAO имеют префикс "CDao".  Можно получить доступ к источнику данных ODBC с помощью классов DAO.  В общем случае классы MFC DAO способны на основе более чем классы MFC на основе ODBC.  DAO\- на основе классы могут получить доступ к данным, включая через драйвер ODBC через собственный компонент database engine.  Они также поддерживают операции языка описания данных DDL \(язык DDL\), такие как добавление таблицы с помощью классов DAO, а не вызывать самого себя.  
  
> [!NOTE]
>  Обмен полями записей \(DFX DAO\) очень похоже на запись обмену полями записей \(RFX\) в зависимости от ODBC\- классы баз данных MFC \(`CDatabase`, `CRecordset`\).  Если вы понимаете RFX, можно найти его простые для использования DFX.  
  
 Объект `CDaoFieldExchange` предоставляет контекстные сведения, необходимые для обмена полей записей DAO, чтобы помнить.  Объекты `CDaoFieldExchange` поддерживают несколько операций, включая параметры привязки и элементы данных полей и флаги параметров различные в полях текущей записи.  Выполняются операции DFX для элементов данных установлен записей\- класса `enum`**FieldType** типов, определенных в `CDaoFieldExchange`.  Возможные значения **FieldType**:  
  
-   **CDaoFieldExchange::outputColumn** для элементов данных полей.  
  
-   **CDaoFieldExchange::param** для элементов данных параметров.  
  
 Функция\-член [IsValidOperation](../Topic/CDaoFieldExchange::IsValidOperation.md) предоставляется для написания собственных пользовательских процедур DFX.  [SetFieldType](../Topic/CDaoFieldExchange::SetFieldType.md) часто будут использоваться в функциях [CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md).  Дополнительные сведения о функциях DFX глобальных см. в разделе [Функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md).  Дополнительные сведения о записи пользовательских подпрограммах DFX для собственных типов данных см. в разделе [Техническая примечание 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).  
  
## Иерархия наследования  
 `CDaoFieldExchange`  
  
## Требования  
 **Header:**  afxdao.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)