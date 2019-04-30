---
title: Изменения, которые можно вносить в код по умолчанию (доступ к данным MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
ms.openlocfilehash: fc448ae1e13025a83b33386c2845bdf7bb4d5eec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398029"
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>Изменения, которые можно вносить в код по умолчанию (доступ к данным MFC)

[Мастер приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md) создает класс записей, выбирающий все записи в одной таблице. Часто требуется изменить такое поведение одним или несколькими из следующих способов:

- Задание фильтра или порядка сортировки для набора записей. Это можно сделать `OnInitialUpdate` после создания объекта набора записей в но перед его `Open` вызывается функция-член. Дополнительные сведения см. в разделе [набор записей: Фильтрация записей (ODBC)](../data/odbc/recordset-filtering-records-odbc.md) и [набор записей: Сортировка записей (ODBC)](../data/odbc/recordset-sorting-records-odbc.md).

- Параметризация набора записей. Укажите значение фактического параметра времени выполнения после фильтра. Дополнительные сведения см. в разделе [набор записей: Параметризация набора записей (ODBC)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

- Передача настроенной строки SQL для [откройте](../mfc/reference/crecordset-class.md#open) функция-член. Описание можно выполнить с помощью этого способа, см. в разделе [SQL: Настройка инструкции SQL набора записей (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

## <a name="see-also"></a>См. также

[Использование представления записей](../data/using-a-record-view-mfc-data-access.md)