---
title: "Графические объекты | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- HRGN
- HFONT
- HBITMAP
dev_langs: C++
helpviewer_keywords:
- CRgn class [MFC], HRGN handle type
- HPEN [MFC]
- objects [MFC], graphic
- palettes [MFC], creating in device context
- pens [MFC], creating in device context
- bitmaps [MFC], creating in device contexts
- palette objects [MFC]
- memory [MFC], display contexts
- MFC, graphic objects
- regions [MFC], creating in device context
- CPen class [MFC], HPEN handle type
- GDI objects [MFC]
- HRGN [MFC]
- graphic objects [MFC]
- GDI objects [MFC], graphic-object classes
- CFont class [MFC], HFONT handle type
- HFONT and class CFont [MFC]
- HBITMAP and class CBitmap [MFC]
- fonts [MFC], creating in device context
- images [MFC], graphic objects [MFC]
- CBitmap class [MFC], HBITMAP handle type
- HPALETTE and class CPalette [MFC]
- CBrush class [MFC], HBRUSH handle type
- objects [MFC], graphic objects
- drawing [MFC], in device contexts
- device contexts [MFC], graphic objects [MFC]
- brushes [MFC], creating in device context
- region objects [MFC]
- pen objects [MFC]
- GDI [MFC], graphic-object classes
- graphic objects [MFC], creating in device context
- HBRUSH and class CBrush [MFC]
- painting and device context [MFC]
- CPalette class [MFC], HPALETTE handle type
ms.assetid: 41963b25-34b7-4343-8446-34ba516b83ca
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0fabeeae17b5bc81fdf592ed452a088b75bae544
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="graphic-objects"></a>Графические объекты
Windows предоставляет широкий набор инструментов рисования для использования в контексте устройств. В их числе перья для рисования линий, кисти для заливки фигур и шрифты для текста. MFC предоставляет классы графических объектов, эквивалентные инструментам рисования в Windows. В таблице ниже показаны доступные классы и эквивалентные типы дескрипторов интерфейса графических устройств (GDI).  
  
> [!NOTE]
>  GDI+ входит в состав Windows XP и доступен в виде распространяемого пакета для Windows NT 4.0 с пакетом обновления 6 (SP6), Windows 2000, Windows 98 и Windows Me. Загрузке последнего распространяемого пакета см. в разделе [http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm](http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm). Дополнительные сведения см. в документации GDI + SDK на: [http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/GDIPlus/GDIPlus.asp](http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/gdiplus/gdiplus.asp).  
  
 В этой статье описывается использование классов графических объектов:  
  
### <a name="classes-for-windows-gdi-objects"></a>Классы для объектов Windows GDI  
  
|Класс|Тип дескриптора Windows|  
|-----------|-------------------------|  
|[CPen](../mfc/reference/cpen-class.md)|`HPEN`|  
|[CBrush](../mfc/reference/cbrush-class.md)|`HBRUSH`|  
|[CFont](../mfc/reference/cfont-class.md)|**HFONT**|  
|[CBitmap](../mfc/reference/cbitmap-class.md)|`HBITMAP`|  
|[CPalette](../mfc/reference/cpalette-class.md)|`HPALETTE`|  
|[CRgn](../mfc/reference/crgn-class.md)|**HRGN**|  
  
> [!NOTE]
>  Класс [CImage](../atl-mfc-shared/reference/cimage-class.md) предоставляет улучшенную поддержку растровых изображений.  
  
 У каждого класса графического объекта в библиотеке есть конструктор, позволяющий создавать графические объекты этого класса, которые необходимо затем инициализировать с помощью соответствующей функции создания, такой как `CreatePen`.  
  
 У каждого класса графического объекта в библиотеке есть оператор приведения, который преобразует объект MFC в связанный дескриптор Windows. Полученный дескриптор допустим, пока связанный объект не отсоединит его. Используйте метод объекта **отсоединения** функции-члена для отсоединения дескриптора.  
  
 Следующий пример кода преобразует объект `CPen` в дескриптор Windows:  
  
 [!code-cpp[NVC_MFCDocViewSDI#5](../mfc/codesnippet/cpp/graphic-objects_1.cpp)]  
  
#### <a name="to-create-a-graphic-object-in-a-device-context"></a>Создание графического объекта в контексте устройства  
  
1.  Определите графический объект в кадре стека. Инициализируйте объект с помощью функции создания определенного типа, такой как `CreatePen`. Или же инициализируйте объект в конструкторе. В описании [одноэтапного и двухэтапного создания](../mfc/one-stage-and-two-stage-construction-of-objects.md), который содержит пример кода.  
  
2.  [Выберите объект в контексте текущего устройства](../mfc/selecting-a-graphic-object-into-a-device-context.md), сохранение старый графический объект, выбранный ранее.  
  
3.  Завершив работу с текущим графическим объектом, выберите старый объект в контексте устройства, чтобы восстановить его состояние.  
  
4.  Разрешите автоматическое удаление выделенного в кадре графического объекта при выходе из области.  
  
> [!NOTE]
>  Если вы будете многократно использовать графический объект, можно выделить его один раз и выбирать в контексте устройства каждый раз, когда он нужен. Не забудьте удалить такой объект, когда он больше не требуется.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Одноэтапное и двухэтапное Создание графических объектов](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Пример построения пера в один и два этапа](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Выбор графического объекта в контексте устройства](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [Контексты устройств](../mfc/device-contexts.md)  
  
-   [Ограничения CImage в ранних версиях операционных систем](../mfc/cimage-limitations-with-earlier-operating-systems.md)  
  
## <a name="see-also"></a>См. также  
 [Объекты окон](../mfc/window-objects.md)

