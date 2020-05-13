---
title: Обмен данными в представлениях записей (доступ к данным MFC)
ms.date: 11/19/2018
helpviewer_keywords:
- RFX (record field exchange), data exchange mechanism
- RFX (record field exchange), record views
- record views, data exchange
- DDX (dialog data exchange), record views
- RFX (record field exchange)
ms.assetid: abc52ca7-6997-47a7-98f3-f347f52b1f72
ms.openlocfilehash: f9f460305b55a2313b64effdf4d1dbbfd9823def
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213477"
---
# <a name="data-exchange-for-record-views---mfc-data-access"></a>Обмен данными в представлениях записей (доступ к данным MFC)

При использовании [добавления класса](../mfc/reference/adding-an-mfc-odbc-consumer.md) для отображения элементов управления в ресурсе шаблона диалогового окна представления записей в поля набора записей платформа управляет обменом данными в обоих направлениях — от набора записей до элементов управления и от элементов управления до набора записей. Использование механизма DDX означает, что нет необходимости писать код передачи данных туда и обратно самостоятельно.

DDX для представлений записей работает совместно с [RFX](../data/odbc/record-field-exchange-rfx.md) для наборов записей класса `CRecordset` (ODBC).  RFX перемещает данные между текущей записью источника данных и полями данных поля объекта Recordset. DDX перемещает данные из элементов данных полей в элементы управления в форме. Данная комбинация заполняет элементы управления формы в начале и по мере того как пользователь перемещается от записи к записи. Также может перемещать обновленные данные обратно в набор записей, а затем в источник данных.

На следующем рисунке показана связь между DDX и RFX для представлений записей.

![Обмен&#45;данными диалоговых окон&#45;и обмен полями записей](../data/media/vc37xt1.gif "Обмен&#45;данными диалоговых окон&#45;и обмен полями записей")<br/>
Обмен данными в диалоговом окне и обмен полями записи

Дополнительные сведения об DDX см [обмен данными окон и проверка](../mfc/dialog-data-exchange-and-validation.md). Дополнительные сведения о RFX см. в статье [Обмен полями записей (RFX)](../data/odbc/record-field-exchange-rfx.md).

## <a name="see-also"></a>См. также раздел

[Представления записей (доступ к данным MFC)](../data/record-views-mfc-data-access.md)<br/>
[Список драйверов ODBC](../data/odbc/odbc-driver-list.md)
