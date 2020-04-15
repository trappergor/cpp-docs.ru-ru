---
title: 'Обработчики команд для прокрутки записей (доступ к данным MFC) '
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
ms.openlocfilehash: 14ef845c3029f1d9a30d257f91c1b33017b6ec8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336943"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>Обработчики команд для прокрутки записей (доступ к данным MFC) 

Класс [CRecordView](../mfc/reference/crecordview-class.md) обеспечивает обработку команд по умолчанию для следующих стандартных команд:

- ID_RECORD_MOVE_FIRST

- ID_RECORD_MOVE_LAST

- ID_RECORD_MOVE_NEXT

- ID_RECORD_MOVE_PREV

Функция `OnMove` члена обеспечивает обработку команд по умолчанию для всех четырех команд, которые переходят от записи к записи. Если команды даны, RFX (или DFX) загружает новую запись в поля набора записей и DDX передвигает значения в элементы управления формы записи. Для получения информации о RFX, [см.](../data/odbc/record-field-exchange-rfx.md)

> [!NOTE]
> Обязательно используйте стандартные идентификаторы команд для любых объектов пользовательского интерфейса, связанных с стандартными командами перехода к записи.

## <a name="see-also"></a>См. также раздел

[Поддержка навигации в представлении записей](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)
