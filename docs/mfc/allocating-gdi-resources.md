---
title: "Выделение ресурсов GDI | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ef6b784a04b7be29b470b92aa09bef8bda449e2
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="allocating-gdi-resources"></a>Выделение ресурсов GDI
В этой статье объясняется, как выделять и освобождать объекты интерфейса графических устройств (GDI) Windows, необходимые для печати.  
  
> [!NOTE]
>  Дополнительные сведения см. в документации GDI + SDK на: [http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/GDIPlus/GDIPlus.asp](http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/gdiplus/gdiplus.asp).  
  
 Предположим, что вам требуется использовать определенные шрифты, перья или другие объекты GDI для печати, но не для отображения на экране. Из-за необходимого им объема памяти неэффективно выделить эти объекты при запуске приложения. Если приложение не печатает документ, эта память может потребоваться для других целей. Лучше выделить их, когда печать начинается, и затем удалите их.  
  
 Чтобы выделить эти объекты GDI, переопределите [OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting) функции-члена. Эта функция хорошо подходит для этой цели по двум причинам: платформа вызывает эту функцию один раз в начале каждого задания печати и, в отличие от [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting), эта функция имеет доступ к [CDC](../mfc/reference/cdc-class.md) Объект, представляющий драйвер принтера. Можно сохранить эти объекты для использования во время выполнения задания печати, определив переменные-члены в классе представления, которые указывают на объекты GDI (например, **CFont \***  члены и т. д).  
  
 Чтобы использовать созданные объекты GDI, выберите их в контексте устройства принтера в [OnPrint](../mfc/reference/cview-class.md#onprint) функции-члена. Если вам требуются различные объекты GDI для разных страниц документа, можно изучить `m_nCurPage` членом [CPrintInfo](../mfc/reference/cprintinfo-structure.md) и выбрать объект GDI соответствующим образом. Если вам требуется объект GDI для нескольких последовательных страниц, в Windows необходимо выбирать его в контексте устройства при каждом вызове `OnPrint`.  
  
 Чтобы освободить эти объекты GDI, переопределите [OnEndPrinting](../mfc/reference/cview-class.md#onendprinting) функции-члена. Платформа вызывает эту функцию в конце каждой задачи печати, что дает вам возможность освободить объекты GDI для печати перед возвратом приложения к другим задачам.  
  
## <a name="see-also"></a>См. также  
 [Печать](../mfc/printing.md)   
 [Печать по умолчанию](../mfc/how-default-printing-is-done.md)

