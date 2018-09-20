---
title: Оптимизация рисования элементов управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7cf929f55b2333bf40cf6fd4ac2588ce17842312
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377790"
---
# <a name="optimizing-control-drawing"></a>Оптимизация рисования элементов управления

Если элемент управления является нарисовать сам себя в контексте устройства, предоставляемую контейнер, он обычно выбирает объекты GDI (например, перья, кисти и шрифты) в контексте устройства, выполняет операции рисования и восстанавливает предыдущий объекты GDI. Если контейнер имеет несколько элементов управления, которые должны отображаться в том же контексте устройства, а каждый элемент управления выбирает необходимые объекты GDI, время можно сохранить, если элементы управления не следует восстанавливать по отдельности ранее выбранные объекты. После всех элементов управления, контейнер можно автоматически восстановить исходные объекты.

Чтобы определить, поддерживает ли контейнер этой методики, можно вызвать элемент управления [COleControl::IsOptimizedDraw](../mfc/reference/colecontrol-class.md#isoptimizeddraw) функция-член. Если эта функция возвращает **TRUE**, элемент управления можно пропустить шаг обычный восстановления ранее выбранные объекты.

Рассмотрим элемент управления, имеющий следующее (неоптимизированные) `OnDraw` функции:

[!code-cpp[NVC_MFC_AxOpt#15](../mfc/codesnippet/cpp/optimizing-control-drawing_1.cpp)]

Перо и кисть в этом примере являются локальными переменными, то есть деструкторы, будет вызываться, когда они выходят за пределы области действия (при `OnDraw` функции завершается). Деструкторы попытается удалить соответствующие объекты GDI. Но они не должны удаляться при оставить их помещения контекст устройства при возвращении с `OnDraw`.

Чтобы предотвратить [CPen](../mfc/reference/cpen-class.md) и [CBrush](../mfc/reference/cbrush-class.md) объектов от уничтожения после `OnDraw` завершения, хранить их в переменных-членов вместо локальных переменных. В объявлении класса элемента управления Добавление объявления для две новые переменные-члены:

[!code-cpp[NVC_MFC_AxOpt#16](../mfc/codesnippet/cpp/optimizing-control-drawing_2.h)]
[!code-cpp[NVC_MFC_AxOpt#17](../mfc/codesnippet/cpp/optimizing-control-drawing_3.h)]

Затем `OnDraw` функции можно переписать следующим образом:

[!code-cpp[NVC_MFC_AxOpt#18](../mfc/codesnippet/cpp/optimizing-control-drawing_4.cpp)]

Такой подход позволяет избежать создания перо и кисть каждый раз `OnDraw` вызывается. Улучшение скорости наносит ущерб поддержку дополнительного экземпляра данных.

При изменении свойства ForeColor или BackColor пера или кисти необходимо создать заново. Чтобы сделать это, переопределите [OnForeColorChanged](../mfc/reference/colecontrol-class.md#onforecolorchanged) и [OnBackColorChanged](../mfc/reference/colecontrol-class.md#onbackcolorchanged) функции-члены:

[!code-cpp[NVC_MFC_AxOpt#19](../mfc/codesnippet/cpp/optimizing-control-drawing_5.cpp)]

Наконец чтобы исключить ненужные `SelectObject` изменить вызовы, `OnDraw` следующим образом:

[!code-cpp[NVC_MFC_AxOpt#20](../mfc/codesnippet/cpp/optimizing-control-drawing_6.cpp)]

## <a name="see-also"></a>См. также

[Элементы ActiveX в MFC. Оптимизация](../mfc/mfc-activex-controls-optimization.md)<br/>
[Класс COleControl](../mfc/reference/colecontrol-class.md)<br/>
[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)<br/>
[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)<br/>
[Мастер элементов ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md)<br/>
[Элементы ActiveX в MFC. Закраска элементов ActiveX](../mfc/mfc-activex-controls-painting-an-activex-control.md)

