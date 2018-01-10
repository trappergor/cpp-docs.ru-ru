---
title: "Запишите обмен (полями записей RFX) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- RFX (ODBC) [C++]
- data [MFC], moving between sources and recordsets
- database classes [C++], RFX
- data [MFC]
- ODBC [C++], RFX
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 50fc0aea1ef50124cd98b0d0498b767d1f00e5c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="record-field-exchange-rfx"></a>Обмен данными полями записей (RFX)
Классы баз данных MFC ODBC автоматизируют перемещение данных между источника данных и [записей](../../data/odbc/recordset-odbc.md) объекта. При наследовании от класса [CRecordset](../../mfc/reference/crecordset-class.md) и выборка строк не используется, данные передаются с помощью механизма обмена (полями записей RFX) поле записи.  
  
> [!NOTE]
>  При реализации массовой выборки строк в производном `CRecordset` класса, платформа использует механизм обмена (полями записей Bulk RFX) массового поле записи для передачи данных. Дополнительные сведения см. в разделе [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 RFX аналогичен обмен данными (диалоговых окон DDX). Перемещение данных между источником данных и элементами данных полей в наборе записей требует нескольких вызовов в набор записей [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) и серьезного взаимодействия между framework и [ODBC](../../data/odbc/odbc-basics.md). Механизм RFX является строго типизированным и избавляет от вызова функций ODBC, такие как **:: SQLBindCol**. Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).  
  
 RFX является наиболее прозрачным. При объявлении классов набора записей с помощью мастера приложений MFC или **добавить класс** (как описано в [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)), RFX встраивается в них автоматически. Класс набора записей должен быть производным от базового класса `CRecordset` предоставляемого платформой. Мастер приложений MFC позволяет создавать исходный класс набора записей. **Добавьте класс** позволяет добавлять другие классы набора записей при необходимости. Дополнительные сведения и примеры см. в разделе [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Необходимо вручную добавить небольшой объем кода RFX в трех случаях, если вы хотите:  
  
-   Используйте параметризованные запросы. Дополнительные сведения см. в разделе [набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
-   Выполнение соединений (с помощью одного набора записей для столбцов из двух или более таблиц). Дополнительные сведения см. в разделе [набор записей: выполнение Join (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).  
  
-   Динамическая привязка столбцов данных. Это реже, чем параметризации. Дополнительные сведения см. в разделе [набор записей: динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 Если требуется более глубоким пониманием RFX см [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 Сведения об использовании объектов наборов записей в следующих разделах:  
  
-   [Обмен данными с полями записей. Использование RFX](../../data/odbc/record-field-exchange-using-rfx.md)  
  
-   [Обмен полями записей. Использование функций RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)  
  
-   [Обмен данными с полями записей. Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)  
  
## <a name="see-also"></a>См. также  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Потребление MFC ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Поддержка базы данных, мастер приложений MFC](../../mfc/reference/database-support-mfc-application-wizard.md)   
 [Класс CRecordset](../../mfc/reference/crecordset-class.md)