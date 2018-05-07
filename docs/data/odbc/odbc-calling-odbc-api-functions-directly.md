---
title: 'ODBC: Непосредственно вызов ODBC API функции | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC API functions [C++], calling
- ODBC [C++], catalog functions
- ODBC API functions [C++]
- APIs [C++], calling
- ODBC classes [C++], vs. ODBC API
- direct ODBC API calls
- catalog functions (ODBC)
- catalog functions (ODBC), calling
- ODBC [C++], API functions
ms.assetid: 4295f1d9-4528-4d2e-bd6a-c7569953c7fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 55b95c5dd48631f9c724aebd163ce948c3469850
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC. Прямой вызов функций ODBC API
Классы баз данных предоставляют более простой интерфейс для [источника данных](../../data/odbc/data-source-odbc.md) сравнению с ODBC. В результате классы не могут инкапсулировать ODBC API. Функциональные возможности за пределами возможностей классов необходимо вызвать функций ODBC API напрямую. Например, необходимо вызывать функции каталога ODBC (**:: SQLColumns**, **:: SQLProcedures**, **:: SQLTables**и другие) напрямую.  
  
> [!NOTE]
>  Источники данных ODBC доступны через классы MFC ODBC, как описано в этом разделе, или с помощью классов MFC объекта доступа к данным (DAO).  
  
 Попытка вызова функции ODBC API напрямую, необходимо выполнить те же действия, выполняемые, если вы вызовы без поддержки платформы. Они являются действия:  
  
-   Выделения хранилища для результатов, возвращаемых.  
  
-   Передайте ODBC **HDBC** или **HSTMT** обработки, в зависимости от того, сигнатура параметра функции. Используйте [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv) макрос, чтобы извлечь дескриптор ODBC.  
  
     Переменные-члены **CDatabase::m_hdbc** и **CRecordset::m_hstmt** доступны, чтобы выделить и инициализировать не нужно.  
  
-   Возможный вызов дополнительных функций ODBC или дальнейшие вызов основной.  
  
-   После отмены выделения хранилища.  
  
 Дополнительные сведения об этих действиях см. в разделе [Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) SDK в документации MSDN.  
  
 Помимо этих шагов необходимо выполнить дополнительные шаги, чтобы проверить возвращаемые значения функции, убедитесь, что программа не ожидает асинхронного вызова для завершения и т. д. Эти действия можно упростить с помощью `AFX_SQL_ASYNC` и `AFX_SQL_SYNC` макросы. Дополнительные сведения см. в разделе [макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md) в *Справочник по библиотеке MFC*.  

  
## <a name="see-also"></a>См. также  
 [Основы ODBC](../../data/odbc/odbc-basics.md)
