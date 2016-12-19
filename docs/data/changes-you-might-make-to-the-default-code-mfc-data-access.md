---
title: "Изменения, которые можно вносить в код по умолчанию (доступ к данным MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "представления записей [C++], настройка кода по умолчанию"
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Изменения, которые можно вносить в код по умолчанию (доступ к данным MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Мастер приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md) создает класс записей для вас, выбирающий все записи в одной таблице.  Часто требуется изменить такое поведение одним или несколькими из следующих способов:  
  
-   Задание фильтра или порядка сортировки для набора записей.  Сделайте это в `OnInitialUpdate` после создания объекта набора записей, но до вызова его функции\-члена **открыть**.  Дополнительные сведения содержатся в разделе [набор записей](../data/odbc/recordset-filtering-records-odbc.md).[](../data/odbc/recordset-filtering-records-odbc.md "Recordset: Filtering Records (ODBC)")[Filtering Records \(ODBC\)](../data/odbc/recordset-filtering-records-odbc.md) и [Recordset:](../data/odbc/recordset-sorting-records-odbc.md)[](../data/odbc/recordset-sorting-records-odbc.md "Recordset: Sorting Records (ODBC)")[Sorting Records \(ODBC\)](../data/odbc/recordset-sorting-records-odbc.md).  
  
-   Параметризация набора записей.  Укажите значение фактического параметра времени выполнения после фильтра.  Дополнительные сведения содержатся в разделе [набор записей](../data/odbc/recordset-parameterizing-a-recordset-odbc.md).[Параметризация набора записей \(ODBC\)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
-   Передача настроенной строки SQL для функции\-члена [открыть](../Topic/CRecordset::Open.md).  Обсуждение того, что можно выполнить с помощью этого способа, см [SQL:](../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md).[](../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md "SQL: Customizing Your Recordset’s SQL Statement (ODBC)")[Настройка инструкции SQL \(ODBC\) набора записей](../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md).  
  
## См. также  
 [Использование представления записей](../data/using-a-record-view-mfc-data-access.md)