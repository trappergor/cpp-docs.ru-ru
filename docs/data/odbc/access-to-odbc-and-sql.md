---
title: Доступ к ODBC и SQL
ms.date: 11/04/2016
helpviewer_keywords:
- API calls [C++], calling DAO or ODBC directly
- Windows API [C++], calling from MFC
- ODBC API functions [C++]
- ODBC API functions [C++], calling from MFC
- SQL [C++], calling ODBC API functions
- ODBC [C++], API functions
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
ms.openlocfilehash: 7a539d911bbf4f4d9582da0ebedaeffaa0d8fa7b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030158"
---
# <a name="access-to-odbc-and-sql"></a>Доступ к ODBC и SQL

Библиотеки Microsoft Foundation Class инкапсулирует большого числа вызовов Windows API и по-прежнему позволяет напрямую вызывать любой функции Windows API. Классы баз данных дают такую же гибкость, что и ODBC API. Хотя классы баз данных обходить сложности ODBC, можно вызывать функции ODBC API непосредственно из любого места в программе.

Аналогично, классы баз данных позволит предотвратить работы с [SQL](../../data/odbc/sql.md), но вы можете использовать SQL напрямую, если требуется. Объекты набора записей можно настроить путем передачи пользовательские инструкции SQL (или часть параметров инструкцию по умолчанию) при открытии набора записей. Вы также можете напрямую с помощью вызовов SQL [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) функция-член класса [CDatabase](../../mfc/reference/cdatabase-class.md).

Дополнительные сведения см. в разделе [ODBC: Вызов ODBC API напрямую функции](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) и [SQL: Выполнение прямых вызовов SQL (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md).

## <a name="see-also"></a>См. также

[ODBC и MFC](../../data/odbc/odbc-and-mfc.md)