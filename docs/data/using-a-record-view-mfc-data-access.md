---
title: Использование представления записей (доступ к данным MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
ms.openlocfilehash: 611ddfd755eec84d4f2572a50c18802f988c5c3d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209031"
---
# <a name="using-a-record-view--mfc-data-access"></a>Использование представления записей (доступ к данным MFC)

В этом разделе объясняется, как настроить код по умолчанию для представлений записей, создаваемых мастером для вас. Как правило, необходимо ограничить выбор записей [фильтром](../data/odbc/recordset-filtering-records-odbc.md) или [параметрами](../data/odbc/recordset-parameterizing-a-recordset-odbc.md), например [Сортировать](../data/odbc/recordset-sorting-records-odbc.md) записи, настраивать инструкцию SQL.

Использование `CRecordView` во многом аналогично использованию метода [CFormView](../mfc/reference/cformview-class.md). Основной подход заключается в использовании представления записей для отображения и возможно, обновления записей одного определенного набора записей. Кроме того, может потребоваться использовать и другие наборы записей, как описано в разделе [представления записей: заполнение списка из второго набора записей](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).

## <a name="see-also"></a>См. также раздел

[Представления записей (доступ к данным MFC)](../data/record-views-mfc-data-access.md)<br/>
[Список драйверов ODBC](../data/odbc/odbc-driver-list.md)
