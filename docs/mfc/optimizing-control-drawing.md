---
title: Оптимизация рисования элементов управления
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
ms.openlocfilehash: 17cb7318e667fe4e16416d51e7e7fba02553cfe6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621015"
---
# <a name="optimizing-control-drawing"></a>Оптимизация рисования элементов управления

Если элементу управления предписывается вывод себя в контекст устройства, предоставляемый контейнером, он обычно выбирает объекты GDI (например, перья, кисти и шрифты) в контексте устройства, выполняет операции рисования и восстанавливает предыдущие объекты GDI. Если контейнер содержит несколько элементов управления, которые должны быть выведены в один и тот же контекст устройства, и каждый элемент управления выбирает необходимые объекты GDI, время можно сохранить, если элементы управления не восстанавливают ранее выбранные объекты. После прорисовки всех элементов управления контейнер может автоматически восстановить исходные объекты.

Чтобы определить, поддерживает ли контейнер этот метод, элемент управления может вызвать функцию-член [COleControl:: исоптимизеддрав](reference/colecontrol-class.md#isoptimizeddraw) . Если эта функция возвращает **значение true**, элемент управления может пропустить нормальный шаг восстановления ранее выбранных объектов.

Рассмотрим элемент управления, имеющий следующую (неоптимизированную) `OnDraw` функцию:

[!code-cpp[NVC_MFC_AxOpt#15](codesnippet/cpp/optimizing-control-drawing_1.cpp)]

В этом примере перо и кисть являются локальными переменными. Это означает, что их деструкторы будут вызываться, когда выходят за пределы области (когда `OnDraw` функция завершается). Деструкторы будут пытаться удалить соответствующие объекты GDI. Но их не следует удалять, если вы планируете оставить их в контексте устройства при возврате из `OnDraw` .

Чтобы предотвратить уничтожение объектов [кпен](reference/cpen-class.md) и [кбруш](reference/cbrush-class.md) по `OnDraw` завершении, сохраните их в переменных членов вместо локальных переменных. В объявлении класса элемента управления добавьте объявления для двух новых переменных члена:

[!code-cpp[NVC_MFC_AxOpt#16](codesnippet/cpp/optimizing-control-drawing_2.h)]
[!code-cpp[NVC_MFC_AxOpt#17](codesnippet/cpp/optimizing-control-drawing_3.h)]

Затем `OnDraw` функция может быть переписана следующим образом:

[!code-cpp[NVC_MFC_AxOpt#18](codesnippet/cpp/optimizing-control-drawing_4.cpp)]

Такой подход позволяет избежать создания пера и кисти при каждом `OnDraw` вызове метода. Повышение скорости достигается за счет обслуживания дополнительных данных экземпляра.

Если свойство ForeColor или BackColor изменяется, перо или кисть необходимо создать снова. Для этого переопределите функции члена [онфореколорчанжед](reference/colecontrol-class.md#onforecolorchanged) и [онбаккколорчанжед](reference/colecontrol-class.md#onbackcolorchanged) :

[!code-cpp[NVC_MFC_AxOpt#19](codesnippet/cpp/optimizing-control-drawing_5.cpp)]

Наконец, чтобы устранить ненужные `SelectObject` вызовы, измените `OnDraw` следующим образом:

[!code-cpp[NVC_MFC_AxOpt#20](codesnippet/cpp/optimizing-control-drawing_6.cpp)]

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX в MFC. Оптимизация](mfc-activex-controls-optimization.md)<br/>
[Класс COleControl](reference/colecontrol-class.md)<br/>
[Элементы ActiveX библиотеки MFC](mfc-activex-controls.md)<br/>
[Мастер элементов ActiveX MFC](reference/mfc-activex-control-wizard.md)<br/>
[Элементы ActiveX в MFC. Закраска элементов ActiveX](mfc-activex-controls-painting-an-activex-control.md)
