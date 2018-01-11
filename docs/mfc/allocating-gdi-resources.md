---
title: "Выделение ресурсов GDI | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7420dbdc1f7560eae9bc5b1a15954c3d68b59678
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="allocating-gdi-resources"></a>Выделение ресурсов GDI
В этой статье объясняется, как выделять и освобождать объекты интерфейса графических устройств (GDI) Windows, необходимые для печати.  
  
> [!NOTE]
>  GDI+ входит в состав Windows XP и доступен в виде распространяемого пакета для Windows NT 4.0 с пакетом обновления 6 (SP6), Windows 2000, Windows 98 и Windows Me. Загрузке последнего распространяемого пакета см. в разделе [http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm](http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm). Дополнительные сведения см. в документации GDI + SDK на: [http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/GDIPlus/GDIPlus.asp](http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/gdiplus/gdiplus.asp).  
  
 Предположим, что вам требуется использовать определенные шрифты, перья или другие объекты GDI для печати, но не для отображения на экране. Из-за необходимого им объема памяти неэффективно выделить эти объекты при запуске приложения. Если приложение не печатает документ, эта память может потребоваться для других целей. Лучше выделить их, когда печать начинается, и затем удалите их.  
  
 Чтобы выделить эти объекты GDI, переопределите [OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting) функции-члена. Эта функция хорошо подходит для этой цели по двум причинам: платформа вызывает эту функцию один раз в начале каждого задания печати и, в отличие от [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting), эта функция имеет доступ к [CDC](../mfc/reference/cdc-class.md) Объект, представляющий драйвер принтера. Можно сохранить эти объекты для использования во время выполнения задания печати, определив переменные-члены в классе представления, которые указывают на объекты GDI (например, **CFont \***  члены и т. д).  
  
 Чтобы использовать созданные объекты GDI, выберите их в контексте устройства принтера в [OnPrint](../mfc/reference/cview-class.md#onprint) функции-члена. Если вам требуются различные объекты GDI для разных страниц документа, можно изучить `m_nCurPage` членом [CPrintInfo](../mfc/reference/cprintinfo-structure.md) и выбрать объект GDI соответствующим образом. Если вам требуется объект GDI для нескольких последовательных страниц, в Windows необходимо выбирать его в контексте устройства при каждом вызове `OnPrint`.  
  
 Чтобы освободить эти объекты GDI, переопределите [OnEndPrinting](../mfc/reference/cview-class.md#onendprinting) функции-члена. Платформа вызывает эту функцию в конце каждой задачи печати, что дает вам возможность освободить объекты GDI для печати перед возвратом приложения к другим задачам.  
  
## <a name="see-also"></a>См. также  
 [Печать](../mfc/printing.md)   
 [Печать по умолчанию](../mfc/how-default-printing-is-done.md)

