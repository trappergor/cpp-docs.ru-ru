---
title: Доступ к ODBC и SQL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- API calls [C++], calling DAO or ODBC directly
- Windows API [C++], calling from MFC
- ODBC API functions [C++]
- ODBC API functions [C++], calling from MFC
- SQL [C++], calling ODBC API functions
- ODBC [C++], API functions
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4fb5daa988614e7e9cb058fce183c6af5b50dd30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="access-to-odbc-and-sql"></a>Доступ к ODBC и SQL
Библиотеки классов Microsoft Foundation инкапсулирует много вызовов Windows API и по-прежнему можно напрямую вызывать любые функции Windows API. Классы баз данных предоставляют такую же гибкость, что и ODBC API. Пока классы баз данных обходить сложности ODBC, можно вызывать функции ODBC API напрямую из любого места в программе.  
  
 Аналогичным образом обходить классы баз данных от необходимости работы с [SQL](../../data/odbc/sql.md), но вы можете использовать SQL непосредственно, если требуется. Можно настроить объекты набора записей, передавая пользовательскую инструкцию SQL (или часть параметров инструкции по умолчанию) при открытии набора записей. Вы также можете напрямую с помощью вызовов SQL [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) функции-члена класса [CDatabase](../../mfc/reference/cdatabase-class.md).  
  
 Дополнительные сведения см. в разделе [ODBC: вызов ODBC API функции напрямую](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) и [SQL: Создание-прямых вызовов SQL (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md).  
  
## <a name="see-also"></a>См. также  
 [ODBC и MFC](../../data/odbc/odbc-and-mfc.md)