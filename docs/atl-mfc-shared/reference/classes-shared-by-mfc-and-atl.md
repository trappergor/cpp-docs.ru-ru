---
title: "Классы, совместно используемые MFC и ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "совместно используемые классы, классы"
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Классы, совместно используемые MFC и ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В следующей таблице перечислены классы, совместно используемые MFC и ATL.  
  
|Класс|Описание|Файл заголовка|  
|-----------|-----------------|-----------------|  
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|Предоставляет методы для управления значений даты и времени, связанного с файлом.|atltime.h|  
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|Предоставляет методы для управления относительных значений даты и времени связанного с файлом.|atltime.h|  
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|Представляет объект строки с фиксированной символьный буфер.|CStringT.h|  
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|Предоставляет поддержку расширенного растровых изображений, включая возможность загрузки и сохранения изображений в формате JPEG, GIF, BMP и Portable Network Graphics (PNG).|atlimage.h|  
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|Инкапсулирует **ДАТЫ** тип данных, используемый в OLE-автоматизации.|atlcomtime.h|  
|[COleDateTimeSpan](../Topic/COleDateTimeSpan%20Class.md)|Представляет относительного времени за период времени.|atlcomtime.h|  
|[CPoint](../Topic/CPoint%20Class.md)|Класс, аналогично Windows [ТОЧКИ](../../mfc/reference/point-structure1.md) Структура, которая также включает функции-члены для управления `CPoint` и **ТОЧКИ** структуры.|atltypes.h|  
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|Класс, аналогично Windows [RECT](RECT%20Structure1.md) Структура, которая также включает функции-члены для управления `CRect` объекты и Windows `RECT` структуры.|atltypes.h|  
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|Представляет `CSimpleStringT` объекта.|atlsimpstr.h|  
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|Класс аналогично Windows РАЗМЕР структуры, которая реализует относительную координату или положение.|atltypes.h|  
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|Предоставляет ресурсов автоматической очистки для `GetBuffer` и `ReleaseBuffer` вызывает на существующих `CStringT` объекта.|atlsimpstr.h|  
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|Представляет данные строкового объекта.|atlsimpstr.h|  
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|Представляет `CStringT` объекта.|atlstr.h CStringT.h (зависит от MFC) (независимый от MFC)|  
|[CTime](../Topic/CTime%20Class.md)|Представляет абсолютное время и дату.|atltime.h|  
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|Количество времени, которые внутренне хранятся как количество секунд в промежутке времени.|atltime.h|  
|[IAtlStringMgr](../Topic/IAtlStringMgr%20Class.md)|Представляет интерфейс для `CStringT` диспетчера памяти.|atlsimpstr.h|  
  
## <a name="see-also"></a>См. также  
 [Классы общих библиотек ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)


