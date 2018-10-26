---
title: 'Дата и время: Поддержка модели автоматизации | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- adding dates
- calculating dates and times
- formatting [Visual Studio], dates
- dates, Automation support
- elapsed time, calculating in Automation
- COleDateTime class, Automation date/time support
- COleDateTimeSpan class, Automation date/time support
- Automation, date and time support
- formatting [Visual Studio], time
- calculations, date and time
- time [Visual Studio], Automation support
ms.assetid: 6eee94c4-943d-4ffc-bf7c-bdda89337ab0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ce0acc7eb90e534e1e66882f5a4a6a88b1eb782
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890183"
---
# <a name="date-and-time-automation-support"></a>Дата и время: Поддержка модели автоматизации

В этой статье описывается, как пользоваться преимуществами служб библиотеки класса, связанных с управлением даты и времени. Процедуры, описанные включают:

- [Получение текущего времени](../atl-mfc-shared/current-time-automation-classes.md)

- [Подсчет затраченного времени](../atl-mfc-shared/elapsed-time-automation-classes.md)

- [Форматирование строковое представление даты и времени](../atl-mfc-shared/formatting-time-automation-classes.md)

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) класс предоставляет способ представления сведения о дате и времени. Она обеспечивает большей степенью детализации и диапазоном больше, чем [CTime](../atl-mfc-shared/reference/ctime-class.md) класса. [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) класс представляет время, например разницу между двумя `COleDateTime` объектов.

`COleDateTime` И `COleDateTimeSpan` классы предназначены для использования с `COleVariant` класс, используемый в службе автоматизации. `COleDateTime` и `COleDateTimeSpan` также полезны в программировании баз данных MFC, но они могут использоваться всякий раз, когда вы хотите управлять значениями даты и времени. Несмотря на то что `COleDateTime` класс имеет больший диапазон значений и большей степенью детализации, чем `CTime` класс, требуется дополнительное хранилище для каждого объекта, чем `CTime`. Существуют также некоторые особые соображения при работе с базовым типом даты. См. в разделе [тип DATE](../atl-mfc-shared/date-type.md) Дополнительные сведения о реализации даты.

`COleDateTime` объекты могут использоваться для представления даты между 1 января 100 и 31 декабря 9999 года. `COleDateTime` объекты являются значениями с плавающей запятой, и приблизительное разрешением 1 миллисекунда. `COleDateTime` на основе типа данных даты, определенные в документации по MFC [COleDateTime::operator даты](../atl-mfc-shared/reference/coledatetime-class.md#operator_date). Фактическая реализация дата выходит за пределы этих границ. `COleDateTime` Реализации налагает эти границы для облегчения работы с классом.

`COleDateTime` не поддерживает юлианскому дат. Предполагается, что григорианского календаря расширение назад во времени в 1 января 100.

`COleDateTime` игнорирует летнее время (DST). В следующем примере сравниваются два метода расчета интервал времени, который пересекает Дата перехода на летнее время переключения: один с помощью CRT и других с помощью `COleDateTime`. Переход на летнее время переключения по, в большинстве регионов в вторую неделю апреля, а третий в октябре.

Первый метод задает два `CTime` объектов, *«время1»* и *time2*, чтобы 5 апреля до 6 апреля соответственно, с помощью стандартной структуры типа C `tm` и `time_t`. Код отображает *«время1»* и *time2* и интервал времени между ними.

Второй метод создает два `COleDateTime` объектов, `oletime1` и `oletime2`и устанавливает их в том же даты в виде *«время1»* и *time2*. Он отображает `oletime1` и `oletime2` и интервал времени между ними.

CRT правильно вычисляет разность 23 часа. `COleDateTimeSpan` Вычисляет разность 24 часа.

[!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]

## <a name="see-also"></a>См. также

[Дата и время](../atl-mfc-shared/date-and-time.md)
