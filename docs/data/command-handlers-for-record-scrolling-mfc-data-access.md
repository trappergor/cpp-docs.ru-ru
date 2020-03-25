---
title: Обработчики команд для прокрутки записей (доступ к данным MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
ms.openlocfilehash: 8bbacd6625e846381d2bafc8133e8b36efe51b1a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213451"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>Обработчики команд для прокрутки записей (доступ к данным MFC)

Класс [CRecordView](../mfc/reference/crecordview-class.md) обеспечивает обработку команд по умолчанию для следующих стандартных команд:

- ID_RECORD_MOVE_FIRST

- ID_RECORD_MOVE_LAST

- ID_RECORD_MOVE_NEXT

- ID_RECORD_MOVE_PREV

Функция члена `OnMove` обеспечивает обработку команд по умолчанию для всех четырех команд, которые переходят от записи к записи. Если команды даны, RFX (или DFX) загружает новую запись в поля набора записей и DDX передвигает значения в элементы управления формы записи. Дополнительные сведения о RFX см. в статье [Обмен полями записей (RFX)](../data/odbc/record-field-exchange-rfx.md).

> [!NOTE]
>  Обязательно используйте стандартные идентификаторы команд для любых объектов пользовательского интерфейса, связанных с стандартными командами перехода к записи.

## <a name="see-also"></a>См. также раздел

[Поддержка навигации в представлении записей](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)
