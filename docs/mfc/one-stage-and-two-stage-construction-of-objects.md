---
title: Одноэтапное и двухэтапное сборка объектов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c53f99932887acad4d2eab5c15ed73b66b359fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346016"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>Одноэтапное и двухэтапное сборка объектов
У вас есть возможность выбора из двух способов создания графических объектов, такие как перья и кисти:  
  
-   *Построение одноэтапного*: создать и инициализировать объект в один этап, все с помощью конструктора.  
  
-   *Двухэтапное создание*: создать и инициализировать объект в два отдельных этапа. Этот конструктор создает объект и функцию инициализации инициализирует его.  
  
 Построение двухэтапное всегда является более безопасным. В один этап построения конструктор может возникнуть исключение, если предоставить неправильные аргументы или сбоя выделения памяти. Эту проблему можно избежать с двух этапов построения, несмотря на то, что необходимо установить флажок для сбоя. В любом случае уничтожения объекта представляет собой один процесс.  
  
> [!NOTE]
>  Эти методы применяются при создании какие-либо объекты, не только графические объекты.  
  
## <a name="example-of-both-construction-techniques"></a>Пример оба способа построения  
 Краткий пример создания объекта перо обоих методов:  
  
 [!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Графические объекты](../mfc/graphic-objects.md)  
  
-   [Выбор графического объекта в контексте устройства](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [Контексты устройств](../mfc/device-contexts.md)  
  
-   [Рисование в представлении](../mfc/drawing-in-a-view.md)  
  
## <a name="see-also"></a>См. также  
 [Графические объекты](../mfc/graphic-objects.md)

