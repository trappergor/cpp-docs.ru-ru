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
ms.openlocfilehash: 208749438f40eef746a638dd12373397c426d454
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368667"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC. Прямой вызов функций ODBC API

Классы баз данных обеспечивают более простой интерфейс для [источника данных,](../../data/odbc/data-source-odbc.md) чем ODBC. В результате классы не инкапсулируют весь API ODBC. Для любой функциональности, которая не входит в возможности классов, необходимо напрямую вызывать функции ODBC API. Например, необходимо позвонить в функции `::SQLProcedures` `::SQLTables`каталога ODBC (,`::SQLColumns`и другие) напрямую.

> [!NOTE]
> Источники данных ODBC доступны через классы MFC ODBC, как описано в этой теме, или через классы MFC Data Access Object (DAO).

Чтобы напрямую вызвать функцию ODBC API, необходимо предпринять те же шаги, что и при совершении вызовов без фреймворка. Они шаги:

- Выделите хранилище для любых результатов, которые возвращает вызов.

- Передайте `HDBC` ODBC `HSTMT` или ручку, в зависимости от подписи параметра функции. Используйте макрос [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv) для получения ручки ODBC.

   Член `CDatabase::m_hdbc` переменных `CRecordset::m_hstmt` и доступны так, что вам не нужно выделять и инициализировать их самостоятельно.

- Возможно, позвоните в дополнительные функции ODBC, чтобы подготовиться или проследить за основным вызовом.

- Распределить хранилище, когда вы закончите.

Более подробную информацию об этих шагах можно узнать в документации MSDN по [вопросам подключения к базе данных (ODBC).](/sql/odbc/microsoft-open-database-connectivity-odbc)

В дополнение к этим шагам, необходимо предпринять дополнительные шаги для проверки значений возврата функций, убедиться, что ваша программа не ждет асинхронного вызова до конца, и так далее. Вы можете упростить эти последние шаги, используя AFX_SQL_ASYNC и AFX_SQL_SYNC макросы. Для получения дополнительной информации, см [Макрос и глобалы](../../mfc/reference/mfc-macros-and-globals.md) в *MFC Справочник*.

## <a name="see-also"></a>См. также раздел

[Основы ODBC](../../data/odbc/odbc-basics.md)
