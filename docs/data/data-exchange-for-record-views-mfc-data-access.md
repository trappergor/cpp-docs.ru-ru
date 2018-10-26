---
title: Обмен данными в представлениях записей (доступ к данным MFC) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RFX (record field exchange), data exchange mechanism
- RFX (record field exchange), record views
- record views, data exchange
- DDX (dialog data exchange), record views
- RFX (record field exchange)
ms.assetid: abc52ca7-6997-47a7-98f3-f347f52b1f72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b6b0109baaf17f804a0ea15eff2e9e766196b86
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052819"
---
# <a name="data-exchange-for-record-views---mfc-data-access"></a>Обмен данными в представлениях записей (доступ к данным MFC)

При использовании [Добавление класса](../mfc/reference/adding-an-mfc-odbc-consumer.md) для сопоставления элементов управления в ресурс шаблона диалоговых окон для просмотра записи полям набора записей, среда управляет обменом данных в обоих направлениях — из набора записей в элементы управления и элементов управления в набор записей. Использование механизма DDX означает, что нет необходимости писать код передачи данных туда и обратно самостоятельно.

DDX для представлений записей работает совместно с [RFX](../data/odbc/record-field-exchange-rfx.md) для набора записей класса `CRecordset` (ODBC).  RFX перемещает данные между текущей записи источника данных и элементами данных полей объекта набора записей. DDX перемещает данные из элементов данных полей в элементы управления в форме. Данная комбинация заполняет элементы управления формы в начале и по мере того как пользователь перемещается от записи к записи. Также может перемещать обновленные данные обратно в набор записей, а затем в источник данных.

На рисунке показана связь между DDX и RFX для представлений записей.

![Диалоговое окно&#45;обмен данными и записи&#45;поле exchange](../data/media/vc37xt1.gif "vc37xt1")<br/>
Обмен данными в диалоговом окне и обмен полями записи

Дополнительные сведения об DDX см [обмен данными окон и проверка](../mfc/dialog-data-exchange-and-validation.md). Дополнительные сведения о RFX см. в разделе [обмен полей записей (RFX)](../data/odbc/record-field-exchange-rfx.md).

## <a name="see-also"></a>См. также

[Представления записей (доступ к данным MFC)](../data/record-views-mfc-data-access.md)<br/>
[Список драйверов ODBC](../data/odbc/odbc-driver-list.md)