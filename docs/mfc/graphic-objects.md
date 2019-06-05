---
title: Графические объекты
ms.date: 11/04/2016
f1_keywords:
- HRGN
- HFONT
- HBITMAP
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
ms.openlocfilehash: 3058bc5793a7766b0a6849ba77f0533f0bbbcef6
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503809"
---
# <a name="graphic-objects"></a>Графические объекты

Windows предоставляет широкий набор инструментов рисования для использования в контексте устройств. В их числе перья для рисования линий, кисти для заливки фигур и шрифты для текста. MFC предоставляет классы графических объектов, эквивалентные инструментам рисования в Windows. В таблице ниже показаны доступные классы и эквивалентные типы дескрипторов интерфейса графических устройств (GDI).

> [!NOTE]
>  Дополнительные сведения см. в разделе [документации GDI + SDK](/windows/desktop/gdiplus/-gdiplus-gdi-start).

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

У каждого класса графического объекта в библиотеке есть оператор приведения, который преобразует объект MFC в связанный дескриптор Windows. Полученный дескриптор допустим, пока связанный объект не отсоединит его. Использование объекта `Detach` функция-член для отсоединения дескриптора.

Следующий пример кода преобразует объект `CPen` в дескриптор Windows:

[!code-cpp[NVC_MFCDocViewSDI#5](../mfc/codesnippet/cpp/graphic-objects_1.cpp)]

#### <a name="to-create-a-graphic-object-in-a-device-context"></a>Создание графического объекта в контексте устройства

1. Определите графический объект в кадре стека. Инициализируйте объект с помощью функции создания определенного типа, такой как `CreatePen`. Или же инициализируйте объект в конструкторе. См. в обсуждении [одноэтапное и двухэтапное создание](../mfc/one-stage-and-two-stage-construction-of-objects.md), который содержит пример кода.

1. [Выберите объект в контексте текущего устройства](../mfc/selecting-a-graphic-object-into-a-device-context.md), сохранении старый графический объект, выбранный ранее.

1. Завершив работу с текущим графическим объектом, выберите старый объект в контексте устройства, чтобы восстановить его состояние.

1. Разрешите автоматическое удаление выделенного в кадре графического объекта при выходе из области.

> [!NOTE]
>  Если вы будете многократно использовать графический объект, можно выделить его один раз и выбирать в контексте устройства каждый раз, когда он нужен. Не забудьте удалить такой объект, когда он больше не требуется.

### <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Одноэтапное и двухэтапное Создание графических объектов](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [Пример построения пера в один и два этапа](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [Выбор графического объекта в контексте устройства](../mfc/selecting-a-graphic-object-into-a-device-context.md)

- [Контексты устройств](../mfc/device-contexts.md)

## <a name="see-also"></a>См. также

[Объекты окон](../mfc/window-objects.md)
