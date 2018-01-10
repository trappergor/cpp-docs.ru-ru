---
title: "Дата и время: Поддержка модели автоматизации | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
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
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6a40a8fe49d9564714c328b657bc0d85d52ad84b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="date-and-time-automation-support"></a>Дата и время: Поддержка автоматизации
В этой статье описывается воспользоваться преимуществами служб библиотеки класса, связанные с управлением даты и времени. Описанные процедуры включают:  
  
-   [Получение текущего времени](../atl-mfc-shared/current-time-automation-classes.md)  
  
-   [Подсчет затраченного времени](../atl-mfc-shared/elapsed-time-automation-classes.md)  
  
-   [Формат строкового представления даты и времени](../atl-mfc-shared/formatting-time-automation-classes.md)  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) класс предоставляет способ представления сведений о дате и времени. Она обеспечивает большую глубину и диапазоном больше, чем [CTime](../atl-mfc-shared/reference/ctime-class.md) класса. [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) класс представляет время, например разницу между двумя `COleDateTime` объектов.  
  
 `COleDateTime` И `COleDateTimeSpan` классы предназначены для использования с `COleVariant` класс, используемый в модели автоматизации. `COleDateTime`и `COleDateTimeSpan` также могут использоваться в программировании баз данных MFC, но они могут использоваться всякий раз, когда требуется работать значений даты и времени. Несмотря на то что `COleDateTime` класс имеет более широкий диапазон значений и высокой степенью детализации, чем `CTime` класса, требуется дополнительное хранилище для каждого объекта, чем `CTime`. Существуют также некоторые специальные рекомендации при работе с основным **даты** типа. В разделе [тип DATE](../atl-mfc-shared/date-type.md) Дополнительные сведения о реализации **даты**.  
  
 `COleDateTime`объекты могут использоваться для представления даты между 1 января 100. и 31 декабря 9999 года. `COleDateTime`объекты являются значения с плавающей запятой, и приблизительное разрешением 1 миллисекунде. `COleDateTime`на основе **даты** типы данных, определенные в документации по MFC под [COleDateTime::operator даты](../atl-mfc-shared/reference/coledatetime-class.md#operator_date). Фактическую реализацию **даты** выходит за пределы этих границ. `COleDateTime` Реализации налагает эти границы, чтобы облегчить работу с данным классом.  
  
 `COleDateTime`не поддерживает юлианский даты. Предполагается, что по григорианскому календарю расширить назад во времени до 1 января 100.  
  
 `COleDateTime`не учитывает переход на летнее время (DST). В следующем примере сравниваются два метода вычисления интервал времени, который пересекает даты переключение летнего времени: один с использованием CRT и другие `COleDateTime`. Летнее время переключения, в большинстве регионов вторую неделю апреля, третья в октябре.  
  
 Первый метод задает два `CTime` объектов, *«время1»* и *time2*, апрель 5 и 6 апреля соответственно, с помощью стандартной структуры типа C **tm** и `time_t`. Код отображает *«время1»* и *time2* и интервал времени между ними.  
  
 Второй метод создает два `COleDateTime` объектов, `oletime1` и `oletime2`и устанавливает их в те же самые даты как *«время1»* и *time2*. Он отображает `oletime1` и `oletime2` и интервал времени между ними.  
  
 CRT правильно вычисляет разность 23 часа. `COleDateTimeSpan`Вычисляет разность 24 часа.  
  
 Обратите внимание, что решения этой проблемы является ближе к концу примере для вывода даты надлежащим образом при использовании `COleDateTime::Format`. См. в статье базы знаний «ошибка: Format("%D") завершается ошибкой для `COleDateTime` и `COleDateTimeSpan`» (Q167338).  
  
 [!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Дата и время](../atl-mfc-shared/date-and-time.md)

