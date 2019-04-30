---
title: 'Обработчики команд для прокрутки записей (доступ к данным MFC) '
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
ms.openlocfilehash: 66944221910dbd23d78a78fc951030efbee86bd0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398049"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>Обработчики команд для прокрутки записей (доступ к данным MFC) 

[CRecordView](../mfc/reference/crecordview-class.md) класс предоставляет обработку по умолчанию для следующих стандартных команд:

- ID_RECORD_MOVE_FIRST

- ID_RECORD_MOVE_LAST

- ID_RECORD_MOVE_NEXT

- ID_RECORD_MOVE_PREV

`OnMove` Функция-член предоставляет обработку по умолчанию для всех четырех команд, при переходе от записи к записи. Если команды даны, RFX (или DFX) загружает новую запись в поля набора записей и DDX передвигает значения в элементы управления формы записи. Дополнительные сведения о RFX см. в разделе [обмен полей записей (RFX)](../data/odbc/record-field-exchange-rfx.md).

> [!NOTE]
>  Обязательно используйте стандартные идентификаторы команд для любых объектов пользовательского интерфейса, связанных с стандартными командами перехода к записи.

## <a name="see-also"></a>См. также

[Поддержка навигации в представлении записей](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)