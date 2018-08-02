---
title: 'ODBC: Непосредственно вызов ODBC API функции | Документация Майкрософт'
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
ms.openlocfilehash: 386bc03234ccb29b293a413944f221189f466c80
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39336599"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC. Прямой вызов функций ODBC API
Классы баз данных предоставляют простой интерфейс для [источника данных](../../data/odbc/data-source-odbc.md) сравнению с ODBC. Таким образом классы не могут инкапсулировать все API-Интерфейс ODBC. Какие-либо возможности, которая выходит за пределы возможностей классов необходимо вызвать функций ODBC API напрямую. Например, необходимо вызвать функций каталога ODBC (`::SQLColumns`, `::SQLProcedures`, `::SQLTables`и другие) напрямую.  
  
> [!NOTE]
>  Источники данных ODBC доступны через классы MFC ODBC, как описано в этом разделе, или с помощью классов MFC объекта доступа к данным (DAO).  
  
 Для вызова функции ODBC API напрямую, необходимо выполнить те же действия, выполняемые если вызовы без framework. Они являются действия:  
  
-   Выделение хранилища для результатов, возвращаемых.  
  
-   Передайте ODBC `HDBC` или `HSTMT` обработки, в зависимости от того, сигнатура параметра функции. Используйте [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv) макрос для получения дескриптора ODBC.  
  
     Переменные-члены `CDatabase::m_hdbc` и `CRecordset::m_hstmt` , поэтому не нужно выделять и инициализировать.  
  
-   Возможно вызовите дополнительные функции ODBC или основной призыв к исполнению.  
  
-   После отмены выделения хранилища.  
  
 Дополнительные сведения об этих действиях см. в разделе [Open Database Connectivity (ODBC)](https://msdn.microsoft.com/library/ms710252.aspx) SDK в документации MSDN.  
  
 В дополнение к эти действия необходимо предпринять дополнительные действия, чтобы проверить возвращаемые значения функции, убедитесь, что программа не находится в состоянии для асинхронного вызова для завершения и т. д. Эти действия можно упростить с помощью макросов AFX_SQL_ASYNC и AFX_SQL_SYNC. Дополнительные сведения см. в разделе [макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md) в *Справочник по библиотеке MFC*.  

## <a name="see-also"></a>См. также  
 [Основы ODBC](../../data/odbc/odbc-basics.md)
