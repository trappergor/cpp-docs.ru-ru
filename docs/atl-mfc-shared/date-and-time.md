---
title: Дата и время | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- time, MFC programming
- time
- MFC, date and time
- dates, MFC
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90317405f09695c57c907e94306623d5b3e2386d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419970"
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

