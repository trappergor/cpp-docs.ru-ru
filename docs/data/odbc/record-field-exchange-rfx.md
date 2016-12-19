---
title: "Обмен данными полями записей (RFX) | Microsoft Docs"
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
  - "данные [MFC]"
  - "данные [MFC], перемещение между ресурсами и наборами записей"
  - "классы баз данных [C++], RFX"
  - "ODBC [C++], RFX"
  - "библиотеки RFX (ODBC) [C++]"
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обмен данными полями записей (RFX)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Классы базы данных MFC ODBC автоматизируют перемещение данных между источником данных и объектом [recordset](../../data/odbc/recordset-odbc.md).  Если класс наследуется от [CRecordset](../Topic/CRecordset%20Class.md) и групповая выборка строк не используется, данные передаются с помощью механизма обмена полями записей \(RFX\).  
  
> [!NOTE]
>  При реализации групповой выборки строк в производном классе `CRecordset` для передачи данных платформой будет использоваться механизм группового обмена полями записей \(Bulk RFX\).  Дополнительные сведения см. в разделе [Набор записей. Групповая выборка записей \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md).  
  
 RFX аналогичен диалоговому обмену данных \(DDX\).  Перемещение данных между источником данных и элементами поля данных набора записей требует многократных вызовов функции набора записей [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) и серьезного взаимодействия между платформой и [ODBC](../../data/odbc/odbc-basics.md).  Механизм RFX является типобезопасным и избавляет от вызова таких функций ODBC, как **::SQLBindCol**.  Дополнительные сведения об обмене данными в диалоговых окнах см. в разделе [Обмен и проверка данных в диалоговых окнах](../../mfc/dialog-data-exchange-and-validation.md).  
  
 RFX является наиболее прозрачным.  При объявлении классов набора записей с помощью мастера приложений MFC или возможности **Добавить класс** \(как описано в [Добавление объекта\-получателя MFC ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)\), RFX встраивается в них автоматически.  Класс набора записей должен быть производным от базового класса `CRecordset` предоставляемого платформой.  Мастер приложений MFC позволяет создавать исходный класс набора записей.  **Добавить класс** позволяет добавлять другие классы набора записей при необходимости.  Дополнительные сведения и примеры см. в разделе [Добавление объекта\-получателя MFC ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Добавлять небольшую часть кода RFX вручную необходимо только в трех случаях, при:  
  
-   Использовании параметризованных запросов.  Дополнительные сведения см. в разделе [Набор записей. Параметризация набора записей \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
-   Выполнении операций объединения \(использовании одного набора записей для столбцов из двух или более таблиц\).  Дополнительные сведения см. в разделе [Набор записей. Объединение \(ODBC\)](../Topic/Recordset:%20Performing%20a%20Join%20\(ODBC\).md).  
  
-   Динамической привязке столбцов данных.  Это является менее распространенным, чем параметризация.  Дополнительные сведения см. в разделе [Набор записей. Динамическая привязка столбцов данных \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 Дополнительные сведения для углубленного понимания RFX см. в разделе [Обмен полями записей. Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 Дополнительные сведения об использовании объектов наборов записей см. в следующих разделах:  
  
-   [Обмен полями записей: использование RFX](../../data/odbc/record-field-exchange-using-rfx.md)  
  
-   [Обмен полями записей: использование функций RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)  
  
-   [Обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)  
  
## См. также  
 [Интерфейс ODBC \(ODBC\)](../Topic/Open%20Database%20Connectivity%20\(ODBC\).md)   
 [Набор записей \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Потребление MFC ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Поддержка базы данных, мастер приложений MFC](../../mfc/reference/database-support-mfc-application-wizard.md)   
 [CRecordset Class](../Topic/CRecordset%20Class.md)