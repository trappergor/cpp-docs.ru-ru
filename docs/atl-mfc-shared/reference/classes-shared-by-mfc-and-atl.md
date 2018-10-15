---
title: Классы, совместно используемые MFC и ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- shared classes, classes
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50295c9d296449e36ed4a305b568d2e0aaed10a3
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2018
ms.locfileid: "49327912"
---
# <a name="classes-shared-by-mfc-and-atl"></a>Классы, совместно используемые MFC и ATL

В следующей таблице перечислены классы, совместно использовать MFC и ATL.

|Класс|Описание|Файл заголовка|
|-----------|-----------------|-----------------|
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|Предоставляет методы для управления значений даты и времени, связанного с файлом.|atltime.h|
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|Предоставляет методы для управления относительных дат и времени значения, связанные с файлом.|atltime.h|
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|Представляет строковый объект с помощью фиксированного символьного буфера.|CStringT.h|
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|Предоставляет улучшенную поддержку растровых изображений, включая возможность загрузки и сохранения изображений в формате JPEG, GIF, BMP и Portable Network Graphics (PNG).|atlimage.h|
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|Инкапсулирует тип данных даты, используемый в OLE-автоматизации.|atlcomtime.h|
|[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)|Представляет относительное время, период времени.|atlcomtime.h|
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|Класс, аналогичный Windows [ТОЧКИ](../../mfc/reference/point-structure.md) структура также включает функции-члены для управления `CPoint` и `POINT` структур.|atltypes.h|
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|Класс, аналогичный Windows [RECT](../../mfc/reference/rect-structure.md) структура также включает функции-члены для управления `CRect` объекты и Windows `RECT` структуры.|atltypes.h|
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|Представляет `CSimpleStringT` объекта.|atlsimpstr.h|
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|Класс, аналогичную структуре размер Windows, реализующий относительные координаты или положение.|atltypes.h|
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|Обеспечивает автоматическое освобождение ресурстов для `GetBuffer` и `ReleaseBuffer` вызывает на имеющихся `CStringT` объекта.|atlsimpstr.h|
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|Представляет данные строкового объекта.|atlsimpstr.h|
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|Представляет `CStringT` объекта.|atlstr.h CStringT.h (зависит от MFC) (независимые от MFC)|
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|Представляет абсолютное время и дату.|atltime.h|
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|Количество времени, который хранится внутренним образом как количество секунд в промежутке времени.|atltime.h|
|[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|Представляет интерфейс для `CStringT` диспетчера памяти.|atlsimpstr.h|

## <a name="see-also"></a>См. также

[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)

