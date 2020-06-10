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
ms.openlocfilehash: a7d038a971fd1d280c100024f8af9a1ec74d8627
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618651"
---
# <a name="graphic-objects"></a>Графические объекты

Windows предоставляет широкий набор инструментов рисования для использования в контексте устройств. В их числе перья для рисования линий, кисти для заливки фигур и шрифты для текста. MFC предоставляет классы графических объектов, эквивалентные инструментам рисования в Windows. В таблице ниже показаны доступные классы и эквивалентные типы дескрипторов интерфейса графических устройств (GDI).

> [!NOTE]
> Дополнительные сведения см. в [документации по пакету SDK для GDI+](/windows/win32/gdiplus/-gdiplus-gdi-start).

В этой статье описывается использование классов графических объектов:

### <a name="classes-for-windows-gdi-objects"></a>Классы для объектов Windows GDI

|Класс|Тип дескриптора Windows|
|-----------|-------------------------|
|[CPen](reference/cpen-class.md)|`HPEN`|
|[CBrush](reference/cbrush-class.md)|`HBRUSH`|
|[CFont](reference/cfont-class.md)|**HFONT**|
|[CBitmap](reference/cbitmap-class.md)|`HBITMAP`|
|[CPalette](reference/cpalette-class.md)|`HPALETTE`|
|[CRgn](reference/crgn-class.md)|**HRGN**|

> [!NOTE]
> Класс [CImage](../atl-mfc-shared/reference/cimage-class.md) предоставляет улучшенную поддержку битовых карт.

У каждого класса графического объекта в библиотеке есть конструктор, позволяющий создавать графические объекты этого класса, которые необходимо затем инициализировать с помощью соответствующей функции создания, такой как `CreatePen`.

У каждого класса графического объекта в библиотеке есть оператор приведения, который преобразует объект MFC в связанный дескриптор Windows. Полученный дескриптор допустим, пока связанный объект не отсоединит его. Используйте `Detach` функцию члена объекта, чтобы отсоединить этот обработчик.

Следующий пример кода преобразует объект `CPen` в дескриптор Windows:

[!code-cpp[NVC_MFCDocViewSDI#5](codesnippet/cpp/graphic-objects_1.cpp)]

#### <a name="to-create-a-graphic-object-in-a-device-context"></a>Создание графического объекта в контексте устройства

1. Определите графический объект в кадре стека. Инициализируйте объект с помощью функции создания определенного типа, такой как `CreatePen`. Или же инициализируйте объект в конструкторе. Ознакомьтесь с обсуждением [создания с одним этапом и двумя этапами](one-stage-and-two-stage-construction-of-objects.md), в котором приводится пример кода.

1. [Выберите объект в текущем контексте устройства](selecting-a-graphic-object-into-a-device-context.md), сохранив старый графический объект, который был выбран ранее.

1. Завершив работу с текущим графическим объектом, выберите старый объект в контексте устройства, чтобы восстановить его состояние.

1. Разрешите автоматическое удаление выделенного в кадре графического объекта при выходе из области.

> [!NOTE]
> Если вы будете многократно использовать графический объект, можно выделить его один раз и выбирать в контексте устройства каждый раз, когда он нужен. Не забудьте удалить такой объект, когда он больше не требуется.

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Одноэтапное и двухэтапное создание графических объектов](one-stage-and-two-stage-construction-of-objects.md)

- [Пример построения пера в один и два этапа](one-stage-and-two-stage-construction-of-objects.md)

- [Выбор графического объекта в контексте устройства](selecting-a-graphic-object-into-a-device-context.md)

- [Контексты устройств](device-contexts.md)

## <a name="see-also"></a>См. также раздел

[Объекты окна](window-objects.md)
