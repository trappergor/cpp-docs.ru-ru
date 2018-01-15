---
title: "Контексты устройств | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OnPrepareDC method [MFC]
- windows [MFC], and device context
- drawing [MFC], device context
- CClientDC class [MFC], and GetDC method [MFC]
- drawing [MFC], in mouse and device contexts
- CDC class [MFC], objects
- device contexts [MFC]
- client areas
- CMetaFileDC class [MFC], and OnPrepareDC method [MFC]
- GDI objects [MFC], device contexts
- graphic objects [MFC], device contexts
- frame windows [MFC], device contexts
- metafiles and device contexts
- EndPaint method [MFC]
- printers [MFC], device contexts
- mouse [MFC], drawing and device contexts
- BeginPaint method, CPaintDC
- CPaintDC class [MFC], device context for painting
- windows [MFC], drawing directly into
- client areas, and device context
- device contexts [MFC], CDC class [MFC]
- user interface [MFC], device contexts
- device-independent drawing
- GetDC method and CClientDC class [MFC]
- CClientDC class [MFC], and ReleaseDC method [MFC]
- ReleaseDC method [MFC]
- device contexts [MFC], about device contexts
- drawing [MFC], directly into windows
- painting and device context
ms.assetid: d0cd51f1-f778-4c7e-bf50-d738d10433c7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 26d4a0e32a8b24a72447cf4227be128659316c0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="device-contexts"></a>Контексты устройств
Контекст устройства — это структура данных Windows, содержащий сведения о замене атрибутов рисования устройства, такие как экран или принтер. Все вызовы рисования выполняются через объект контекста устройства, который инкапсулирует API-интерфейсов Windows для рисования линий, фигур и текста. Контексты устройств разрешить аппаратно независимое рисование в Windows. Контексты устройств можно использовать для рисования на экране, на принтер или в метафайл.  
  
 [CPaintDC](../mfc/reference/cpaintdc-class.md) объектов инкапсулировать распространенных случаях Windows, вызвав `BeginPaint` функция, а затем рисование в контексте устройства, а затем вызов `EndPaint` функции. `CPaintDC` Вызовы конструктора `BeginPaint` для вас и вызывает деструктор `EndPaint`. Упрощенный процесс является создание [CDC](../mfc/reference/cdc-class.md) объекта, рисования и затем удалите `CDC` объекта. В платформе большая часть даже этот процесс выполняется автоматически. В частности к `OnDraw` функции передается `CPaintDC` уже подготовлены (через `OnPrepareDC`), и просто нарисуйте в него. Он будет уничтожен платформой и базового контекста устройства Windows освобождается при возврате из вызова вашей `OnDraw` функции.  
  
 [CClientDC](../mfc/reference/cclientdc-class.md) объектов инкапсулировать работу с контекст устройства, который представляет только клиентской области окна. `CClientDC` Вызовы конструктора `GetDC` функции и вызовы деструктора `ReleaseDC` функции. [CWindowDC](../mfc/reference/cwindowdc-class.md) объектов инкапсулировать контекст устройства, который представляет всего окна, включая его фрейма.  
  
 [CMetaFileDC](../mfc/reference/cmetafiledc-class.md) объектов инкапсуляции рисование в метафайл Windows. В отличие от к `CPaintDC` передаваемый `OnDraw`, в этом случае необходимо вызвать [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) самостоятельно.  
  
## <a name="mouse-drawing"></a>Рисование с помощью мыши  
 Большинство рисование в программу framework и таким образом большинство рабочий контекст устройства — выполняется в режиме `OnDraw` функции-члена. Однако объекты контекста устройства по-прежнему можно использовать для других целей. Например, для обеспечения обратной связи для отслеживания движения мыши в представлении, необходимо нарисовать непосредственно в представление, не дожидаясь `OnDraw` для вызова.  
  
 В этом случае можно использовать [CClientDC](../mfc/reference/cclientdc-class.md) объект контекста устройства для рисования непосредственно в представление.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Контексты устройств (определение)](http://msdn.microsoft.com/library/windows/desktop/dd183553)  
  
-   [Рисование в представлении](../mfc/drawing-in-a-view.md)  
  
-   [Интерпретация ввода пользователя через представление](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [Прямых и кривых линий](http://msdn.microsoft.com/library/windows/desktop/dd145028)  
  
-   [Закрашенные фигуры](http://msdn.microsoft.com/library/windows/desktop/dd162714)  
  
-   [Шрифты и текст](http://msdn.microsoft.com/library/windows/desktop/dd144819)  
  
-   [Цвета](http://msdn.microsoft.com/library/windows/desktop/dd183450)  
  
-   [Координат и преобразования](http://msdn.microsoft.com/library/windows/desktop/dd183475)  
  
## <a name="see-also"></a>См. также  
 [Объекты окон](../mfc/window-objects.md)

