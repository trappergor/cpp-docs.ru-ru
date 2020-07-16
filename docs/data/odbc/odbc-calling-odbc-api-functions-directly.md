---
title: ODBC. Прямой вызов функций ODBC API
ms.date: 11/04/2016
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
ms.openlocfilehash: e1cb5df4a93fc642ccf4d500a5eb93690b0b3d75
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2020
ms.locfileid: "86403831"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC. Прямой вызов функций ODBC API

Классы баз данных предоставляют более простой интерфейс для [источника данных](../../data/odbc/data-source-odbc.md) , чем ODBC. В результате классы не инкапсулируют все API ODBC. Для функций, которые выходят за пределы возможностей классов, необходимо напрямую вызывать функции ODBC API. Например, необходимо напрямую вызывать функции каталога ODBC (,, `::SQLColumns` `::SQLProcedures` `::SQLTables` и др.).

> [!NOTE]
> Источники данных ODBC доступны через классы ODBC MFC, как описано в этом разделе, или через классы объектов доступа к данным MFC (DAO).

Для непосредственного вызова функции ODBC API необходимо выполнить те же действия, что и при выполнении вызовов без платформы. Это следующие шаги:

- Выделение хранилища для любых результатов, возвращаемых вызовом.

- Передайте ODBC `HDBC` или `HSTMT` Handle в зависимости от сигнатуры параметра функции. Используйте макрос [афксжесенв](../../mfc/reference/database-macros-and-globals.md#afxgethenv) для получения маркера ODBC.

   Переменные членов `CDatabase::m_hdbc` и `CRecordset::m_hstmt` доступны, поэтому вам не нужно самостоятельно выделять и инициализировать их.

- Возможно, можно вызвать дополнительные функции ODBC, чтобы подготовиться к основному вызову или выполнить его.

- По завершении освобождает хранилище.

Дополнительные сведения об этих действиях см. в [справочнике программиста по ODBC](/sql/odbc/reference/odbc-programmer-s-reference).

В дополнение к этим действиям необходимо выполнить дополнительные действия для проверки возвращаемых значений функции, убедиться, что программа не ожидает асинхронного вызова и т. д. Эти действия можно упростить с помощью макросов AFX_SQL_ASYNC и AFX_SQL_SYNC. Дополнительные сведения см. в разделе [макросы и глобальные библиотеки MFC](../../mfc/reference/mfc-macros-and-globals.md).

## <a name="see-also"></a>См. также раздел

[Основы ODBC](../../data/odbc/odbc-basics.md)
