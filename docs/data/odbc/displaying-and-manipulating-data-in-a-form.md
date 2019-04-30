---
title: Отображение и обработка данных в форме
ms.date: 11/04/2016
helpviewer_keywords:
- forms [C++], displaying data
- displaying data [C++], forms
- ODBC [C++], forms
- record views [C++], displaying data
- data [MFC]
- data [MFC], displaying in a form
ms.assetid: c56185c4-12cb-40b1-b499-02b29ea83e3a
ms.openlocfilehash: e50c433e701fbae2e607d79d7abb34efe8eba5b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395915"
---
# <a name="displaying-and-manipulating-data-in-a-form"></a>Отображение и обработка данных в форме

Многие приложения доступа к данным выберите данных и отображения его в полях формы. Класс database [CRecordView](../../mfc/reference/crecordview-class.md) дает [CFormView](../../mfc/reference/cformview-class.md) объекта непосредственно соединен с объектом набора записей. Представление записей использует [обмен данными диалоговых окон (DDX)](../../mfc/dialog-data-exchange-and-validation.md) для перемещения значения полей текущей записи из набора записей в элементы управления на форме и возврата обновленных данных в набор записей. Набор записей, в свою очередь, использует обмен полями записей (RFX) для перемещения данных между его поля элементов данных и соответствующих столбцов в таблице в источнике данных.

Можно использовать мастер приложений MFC или **Добавление класса** (как описано в разделе [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) для создания класса представления и его связанным классом набора записей в сочетании.

Представления записей и его записей удаляются при закрытии документа. Дополнительные сведения о представлениях записей, см. в разделе [представления записей](../../data/record-views-mfc-data-access.md). Дополнительные сведения о RFX см. в разделе [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).

## <a name="see-also"></a>См. также

[ODBC и MFC](../../data/odbc/odbc-and-mfc.md)