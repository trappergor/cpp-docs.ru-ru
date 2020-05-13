---
title: Изменения, которые можно вносить в код по умолчанию (доступ к данным MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
ms.openlocfilehash: 7ea616caf176cd1e9e2f26bee1339640067b4e3e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213468"
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>Изменения, которые можно вносить в код по умолчанию (доступ к данным MFC)

[Мастер приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md) записывает класс набора записей, который выбирает все записи в одной таблице. Часто требуется изменить такое поведение одним или несколькими из следующих способов:

- Задание фильтра или порядка сортировки для набора записей. Это делается в `OnInitialUpdate` после создания объекта Recordset, но до вызова функции-члена `Open`. Дополнительные сведения см. в разделе [набор записей: Фильтрация записей (ODBC)](../data/odbc/recordset-filtering-records-odbc.md) и [набор записей: Сортировка записей (ODBC)](../data/odbc/recordset-sorting-records-odbc.md).

- Параметризация набора записей. Укажите значение фактического параметра времени выполнения после фильтра. Дополнительные сведения см [. в разделе набор записей: Параметризация набора записей (ODBC).](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

- Передайте настраиваемую строку SQL в функцию [Open](../mfc/reference/crecordset-class.md#open) Member. Обсуждение того, что можно сделать с помощью этого метода, см. в разделе [SQL: Настройка инструкции SQL набора записей (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

## <a name="see-also"></a>См. также раздел

[Использование представления записей](../data/using-a-record-view-mfc-data-access.md)
