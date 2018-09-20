---
title: Классы инструмента рисования | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.drawing
dev_langs:
- C++
helpviewer_keywords:
- drawing [MFC], tool classes
- screen output classes [MFC]
- output classes [MFC]
ms.assetid: e907bd89-38b5-47c9-b76a-95e0bf3bb41d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9d81f3051450f060a82bbd3a192ad387332922a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408886"
---
# <a name="drawing-tool-classes"></a>Классы инструмента рисования

Эти классы инкапсулируют инструменты рисования, которые используются для прорисовки на контекст устройства.

[CGdiObject](../mfc/reference/cgdiobject-class.md)<br/>
Базовый класс для инструментов для рисования GDI.

[CBrush](../mfc/reference/cbrush-class.md)<br/>
Инкапсулирует кисть GDI, которая может быть выбран в качестве текущей кисти в контексте устройства. Кисти используются для заполнения внутренние изображаемого объектов.

[CPen](../mfc/reference/cpen-class.md)<br/>
Инкапсулирует перо GDI, может быть выбран в качестве текущего пера в контексте устройства. Перья, используются для отображения линий границы объектов.

[CFont](../mfc/reference/cfont-class.md)<br/>
Инкапсулирует шрифт GDI, который может быть выбран в качестве текущего шрифта в контексте устройства.

[CBitmap](../mfc/reference/cbitmap-class.md)<br/>
Инкапсулирует точечный рисунок GDI, предоставляя интерфейс для управления точечных рисунков.

[CPalette](../mfc/reference/cpalette-class.md)<br/>
Инкапсулирует цветовую палитру для использования в качестве интерфейса между приложением и устройство вывода цвета, такое как отображаемое GDI.

[CRectTracker](../mfc/reference/crecttracker-class.md)<br/>
Отображает и обрабатывает пользовательский интерфейс для изменения размеров и перемещение объектов прямоугольной.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)

