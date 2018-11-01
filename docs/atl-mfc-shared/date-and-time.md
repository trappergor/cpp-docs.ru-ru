---
title: Дата и время
ms.date: 11/04/2016
helpviewer_keywords:
- time, MFC programming
- time
- MFC, date and time
- dates, MFC
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
ms.openlocfilehash: dcb5ef9f21987e11608cfa29e77b24e96153e6b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459453"
---
# <a name="date-and-time"></a>Дата и время

MFC поддерживает несколько различных способов работы с датами и временем. Сюда входит следующее.

- Классы общего назначения времени. [CTime](../atl-mfc-shared/reference/ctime-class.md) и [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md) классы инкапсулируют большинство функциональных возможностей, связанных с библиотекой времени стандарту ANSI, который объявляется во времени. З.

- Поддержка системных часов. С MFC версии 3.0, добавлена поддержка для `CTime` для Win32 `SYSTEMTIME` и `FILETIME` типов данных.

- Поддержка автоматизации [тип данных DATE](../atl-mfc-shared/date-type.md). Дата поддерживает даты, времени и значений даты и времени. [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) и [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) классы инкапсулируют эту функцию. Они работают с [COleVariant](../mfc/reference/colevariant-class.md) используя Поддержка модели автоматизации.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Дата и время. Поддержка SYSTEMTIME](../atl-mfc-shared/date-and-time-systemtime-support.md)

- [Дата и время. Поддержка автоматизации](../atl-mfc-shared/date-and-time-automation-support.md)

- [Дата и время. Поддержка базы данных](../atl-mfc-shared/date-and-time-database-support.md)

## <a name="see-also"></a>См. также

[Основные понятия](../mfc/mfc-concepts.md)<br/>
[Общие разделы по MFC](../mfc/general-mfc-topics.md)

