---
title: 'SQL: Выполнение прямых вызовов SQL (ODBC) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- SQL, direct calls from ODBC
- SQL, calling directly from ODBC
- ODBC, SQL calls
- SQL calls
- direct SQL calls from ODBC
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2134fc41b604ffd659f9ee075abc9d462ff4f0db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="sql-making-direct-sql-calls-odbc"></a>SQL. Выполнение прямых вызовов SQL (ODBC)
Содержание раздела:  
  
-   Когда следует использовать прямые SQL вызывает.  
  
-   [Порядок выполнения прямой SQL вызывает к источнику данных](#_core_making_direct_sql_function_calls).  
  
> [!NOTE]
>  Эти сведения относятся к классам MFC ODBC. При работе с классами MFC DAO см. в разделе «Сравнение Microsoft Jet базы данных ядра SQL и ANSI SQL» справки DAO.  
  
##  <a name="_core_when_to_call_sql_directly"></a> Когда прямых вызовов SQL  
 Для создания новых таблиц, и (Удалить) или изменить существующие таблицы, создать индексы и выполнить другие функции SQL, которые изменяют [источника данных (ODBC)](../../data/odbc/data-source-odbc.md) схемы, необходимо выполнить инструкцию SQL непосредственно к источнику данных с использованием базы данных Определение языка DDL. При использовании мастера для создания набора записей для таблицы (во время разработки), можно выбрать, какие столбцы таблицы будут представлять набор записей. Это позволяет запретить для столбцов, которые вы или другой пользователь источника данных, добавьте в таблицу позже, после компиляции программы. Классы баз данных не поддерживают DDL непосредственно, но можно писать код для привязки нового столбца к набору записей динамически во время выполнения. Сведения о том, как сделать этой привязки в разделе [набор записей: динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 Саму СУБД можно использовать для изменения схемы или другого средства, поддерживающие выполнение функций DDL. Вызовы функций ODBC также можно использовать для отправки инструкций SQL, например вызов предопределенного запроса (хранимой процедуры), который не возвращает записи.  
  
##  <a name="_core_making_direct_sql_function_calls"></a> Выполнение прямых вызовов SQL-функция  
 Чтобы выполнить прямой вызов SQL с помощью [CDatabase-класс](../../mfc/reference/cdatabase-class.md) объекта. Настроить строку инструкции SQL (обычно в `CString`) и передать его в [помощью функции CDatabase::ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) функцию-член вашей `CDatabase` объекта. При использовании функции ODBC для отправки инструкции SQL, в которой должны возвращаться записи, записи учитываются.  
  
## <a name="see-also"></a>См. также  
 [SQL](../../data/odbc/sql.md)