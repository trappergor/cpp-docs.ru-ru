---
title: "Классы, совместно используемые MFC и ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- shared classes, classes
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e881c303fc61ee7b72f067b0c9c3378e1e2c1858
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="classes-shared-by-mfc-and-atl"></a>Классы, совместно используемые MFC и ATL
В следующей таблице перечислены классы, совместно MFC и ATL.  
  
|Класс|Описание:|Файл заголовка|  
|-----------|-----------------|-----------------|  
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|Предоставляет методы для управления значений даты и времени, связанного с файлом.|atltime.h|  
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|Предоставляет методы для управления относительных значений даты и времени связанных с файлом.|atltime.h|  
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|Представляет строковый объект с буфером символов фиксированной.|CStringT.h|  
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|Предоставляет улучшенную поддержку растровых изображений, включая возможность загрузки и сохранения изображений в формате JPEG, GIF, BMP и Portable Network Graphics (PNG).|atlimage.h|  
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|Инкапсулирует **даты** тип данных, используемый в OLE-автоматизации.|atlcomtime.h|  
|[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)|Представляет относительного времени временной интервал.|atlcomtime.h|  
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|Класс аналогично Windows [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры, который также включает функции-члены для управления `CPoint` и **ТОЧКИ** структуры.|atltypes.h|  
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|Класс аналогично Windows [RECT](../../mfc/reference/rect-structure1.md) структуры, который также включает функции-члены для управления `CRect` объектов и Windows `RECT` структуры.|atltypes.h|  
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|Представляет `CSimpleStringT` объекта.|atlsimpstr.h|  
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|Класс схожей структурой размер Windows, реализующий относительные координаты или положение.|atltypes.h|  
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|Предоставляет очистку ресурсов, автоматическое для `GetBuffer` и `ReleaseBuffer` вызывает на существующие `CStringT` объекта.|atlsimpstr.h|  
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|Представляет данные строкового объекта.|atlsimpstr.h|  
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|Представляет `CStringT` объекта.|atlstr.h CStringT.h (MFC зависимости) (независимый MFC)|  
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|Представляет абсолютное время и дату.|atltime.h|  
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|Количество времени, которое хранится внутренне как количество секунд в промежутке времени.|atltime.h|  
|[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|Представляет интерфейс для `CStringT` диспетчера памяти.|atlsimpstr.h|  
  
## <a name="see-also"></a>См. также  
 [ATL и MFC общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md)


