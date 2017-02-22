---
title: "Выделение ресурсов GDI | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GDI-объекты, выделение во время печати"
  - "печать [MFC], выделение ресурсов GDI"
  - "ресурсы [MFC], печать"
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Выделение ресурсов GDI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этой статье объясняется, как выделять и освобождать объекты интерфейса графических устройств \(GDI\) Windows, необходимые для печати.  
  
> [!NOTE]
>  GDI\+ входит в состав Windows XP и доступен в виде распространяемого пакета для Windows NT 4.0 с пакетом обновления 6 \(SP6\), Windows 2000, Windows 98 и Windows Me.  Сведения о скачивании последнего распространяемого пакета см. на странице [http:\/\/www.microsoft.com\/msdownload\/platformsdk\/sdkupdate\/psdkredist.htm](http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm).  Подробные сведения см. в документации GDI\+ SDK на портале MSDN: [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/gdicpp\/GDIPlus\/GDIPlus.asp](http://msdn.microsoft.com/library/default.asp?url=/library/gdicpp/GDIPlus/GDIPlus.asp).  
  
 Предположим, что вам требуется использовать определенные шрифты, перья или другие объекты GDI для печати, но не для отображения на экране.  Из\-за необходимого им объема памяти неэффективно выделить эти объекты при запуске приложения.  Если приложение не печатает документ, эта память может потребоваться для других целей.  Лучше выделить их, когда печать начинается, и затем удалите их.  
  
 Чтобы выделить эти объекты GDI, переопределите функцию\-член [OnBeginPrinting](../Topic/CView::OnBeginPrinting.md).  Эта функция хорошо подходит для этой цели по двум причинам: платформа вызывает эту функцию один раз в начале каждого задания печати и, в отличие от [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md), эта функция имеет доступ к объекту [CDC](../Topic/CDC%20Class.md), представляющему драйвер принтера.  Эти объекты можно сохранить во время выполнения задания печати, определив переменные\-члены в классе представления, которые указывают на объекты GDI \(например, **CFont \*** и т. д.\).  
  
 Чтобы использовать созданные объекты GDI, выберите их в контексте устройства принтера в функции\-члене [OnPrint](../Topic/CView::OnPrint.md).  Если вам требуются различные объекты GDI для разных страниц документа, можно изучить элемент `m_nCurPage` структуры [CPrintInfo](../mfc/reference/cprintinfo-structure.md) и выбрать объект GDI соответствующим образом.  Если вам требуется объект GDI для нескольких последовательных страниц, в Windows необходимо выбирать его в контексте устройства при каждом вызове `OnPrint`.  
  
 Чтобы освободить эти объекты GDI, переопределите функцию\-член [OnEndPrinting](../Topic/CView::OnEndPrinting.md).  Платформа вызывает эту функцию в конце каждого задания печати, что дает вам возможность освободить объекты GDI для печати перед возвратом приложения к другим задачам.  
  
## См. также  
 [Печать](../mfc/printing.md)   
 [Печать по умолчанию](../Topic/How%20Default%20Printing%20Is%20Done.md)