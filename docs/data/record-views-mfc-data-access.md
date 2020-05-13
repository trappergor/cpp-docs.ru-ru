---
title: Представления записей (доступ к данным MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], record views
- ODBC recordsets [C++], record views
- databases [C++], record views
- record views [C++]
- forms [C++], data access tasks
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
ms.openlocfilehash: 31dbd92219f263c625050524279b97ef38ba9ba1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209135"
---
# <a name="record-views--mfc-data-access"></a>Представления записей (доступ к данным MFC)

Этот раздел относится только к классам ODBC MFC. Дополнительные сведения о OLE DB представлениях записей см. в разделе [коледбрекордвиев](../mfc/reference/coledbrecordview-class.md) and [using a OLE DB Record views](../data/oledb/using-ole-db-record-views.md).

Для поддержки приложений для доступа к данным на основе форм Библиотека классов предоставляет класс [CRecordView](../mfc/reference/crecordview-class.md). Представление записей — это объект представления формы, элементы управления которого сопоставляются непосредственно элементам данных поля объекта [Recordset](../data/odbc/recordset-odbc.md) (и косвенно соответствуют соответствующим столбцам в результатах запроса или таблице в источнике данных). Как и базовый класс [CFormView](../mfc/reference/cformview-class.md), `CRecordView` основан на ресурсе шаблона диалогового окна.

## <a name="form-uses"></a>Использование форм

Формы полезны для различных задач доступа к данным:

- Ввод данных

- Выполнение анализа данных только для чтения

- Обновление данных

## <a name="further-reading-about-record-views"></a>Дополнительные сведения о представлениях записей

Материалы в следующих разделах относятся к классам и на основе ODBC и на основе DAO . Использование `CRecordView` для ODBC и `CDaoRecordView` для DAO.

Будут рассмотрены следующие задачи:

- [Функции классов представлений записей](../data/features-of-record-view-classes-mfc-data-access.md)

- [Обмен данными с представлениями записей](../data/data-exchange-for-record-views-mfc-data-access.md)

- [Роль в работе с представлением записей](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)

- [Проектирование и создание представления записей](../data/designing-and-creating-a-record-view-mfc-data-access.md)

- [Использование представления записей](../data/using-a-record-view-mfc-data-access.md)

## <a name="see-also"></a>См. также раздел

[Программирование доступа к данным (библиотеки MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[Список драйверов ODBC](../data/odbc/odbc-driver-list.md)
