---
title: Добавление свойства в элемент управления (учебник ATL, часть 3) | Документация Майкрософт
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1e90da3fe44613b0c530e801d963eaddd9d783e
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43756912"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>Добавление свойства в элемент управления (учебник ATL, часть 3)

`IPolyCtl` — Это интерфейс, содержащий элемент управления пользовательских методов и свойств, и будет добавить свойство.

### <a name="to-add-a-property-using-the-add-property-wizard"></a>Чтобы добавить свойства с помощью мастера добавления свойства

1. В представлении классов разверните многоугольника.

2. Щелкните правой кнопкой мыши IPolyCtl.

3. В контекстном меню, щелкните **добавить**, а затем нажмите кнопку **добавить свойство**.

     Появится мастер добавления свойств.

4. В раскрывающемся списке список типов свойств, выберите `SHORT`.

5. Тип *сторон* как **имя свойства.**

6. Нажмите кнопку **Готово** чтобы завершить добавление свойства.

При добавлении свойства к интерфейсу, MIDL (программы, компилирует IDL-файлы) определяет `Get` метод для извлечения его значения и `Put` метод для установки нового значения. Методы именуется путем добавления префикса `put_` и `get_` имени свойства.

Мастер добавления свойств добавляет необходимые строки в IDL-файл. Он также добавляет `Get` и `Put` прототипы в определение класса в PolyCtl.h функции и добавляет пустую реализацию PolyCtl.cpp. Это можно проверить, открыв PolyCtl.cpp и поиске функций `get_Sides` и `put_Sides`.

Несмотря на то, что теперь у вас есть каркас функции задание и получение свойства, ему требуется место для сохранения. Создается переменная для хранения этого свойства и соответствующим образом обновите функции.

#### <a name="to-create-a-variable-to-store-the-property-and-update-the-put-and-get-methods"></a>Для создания переменной для хранения этого свойства, put и с именами методов get

1. В обозревателе решений откройте PolyCtl.h и добавьте следующую строку после определения `m_clrFillColor`:

     [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]

2. Значение по умолчанию `m_nSides`. Сделать по умолчанию фигуры треугольника, добавив строку в конструктор в PolyCtl.h:

     [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]

3. Реализуйте `Get` и `Put` методы. `get_Sides` И `put_Sides` объявления функций были добавлены в PolyCtl.h. Замените код в PolyCtl.cpp для `get_Sides` и `put_Sides` следующим кодом:

     [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]

`get_Sides` Метод возвращает текущее значение `Sides` свойства с помощью `pVal` указатель. В `put_Sides` метод, код обеспечивает пользователю `Sides` свойство допустимым значением. Минимальное значение должно быть 3, а поскольку массив точек будет использоваться для каждой стороны, 100 приемлемого предела для максимального значения.

Теперь у вас есть свойство с именем `Sides`. На следующем шаге мы изменим код прорисовки для его использования.

[Вернитесь к шагу 2](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [к шагу 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)

## <a name="see-also"></a>См. также

[Учебник](../atl/active-template-library-atl-tutorial.md)

