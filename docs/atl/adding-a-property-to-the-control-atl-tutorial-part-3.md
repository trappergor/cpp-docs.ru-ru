---
title: Добавление свойства в элемент управления (учебник ATL, часть 3)
ms.custom: get-started-article
ms.date: 09/26/2018
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
ms.openlocfilehash: 9b8744e964274acb35c32a1ace02f71d0fed5c2d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466863"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>Добавление свойства в элемент управления (учебник ATL, часть 3)

`IPolyCtl` — Это интерфейс, содержащий элемент управления пользовательских методов и свойств, и будет добавить свойство.

### <a name="to-add-the-property-definitions-to-your-project"></a>Чтобы добавить определения свойств в проект

1. В **представление классов**, разверните `Polygon` ветви.

1. Щелкните правой кнопкой мыши `IPolyCtl`.

1. В контекстном меню, щелкните **добавить**, а затем нажмите кнопку **добавить свойство**. **Добавить свойство** отобразится окно мастера.

1. Тип `Sides` как **имя свойства**.

1. В раскрывающемся списке **тип свойства**выберите `short`.

1. Нажмите кнопку **ОК** чтобы завершить добавление свойства.

1. Из **обозревателе решений**откройте Polygon.idl и замените следующие строки в конце `IPolyCtl : IDispatch` интерфейса:

    ```cpp
    short get_Sides();
    void set_Sides(short value);
    ```

    на

    ```cpp
    [propget, id(1), helpstring("property Sides")] HRESULT Sides([out, retval] short *pVal);
    [propput, id(1), helpstring("property Sides")] HRESULT Sides([in] short newVal);
    ```

1. Из **обозревателе решений**откройте PolyCtl.h и добавьте следующие строки после определения `m_clrFillColor`:

    [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]

Несмотря на то, что теперь у вас есть каркас функции задание и получение свойства и переменной для хранения этого свойства, необходимо реализовать функции соответствующим образом.

### <a name="to-update-the-get-and-put-methods"></a>Чтобы обновить get и put методы

1. Значение по умолчанию `m_nSides`. Сделать по умолчанию фигуры треугольника, добавив строку в конструктор в PolyCtl.h:

    [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]

1. Реализуйте `Get` и `Put` методы. `get_Sides` И `put_Sides` объявления функций были добавлены в PolyCtl.h. Теперь добавьте код для `get_Sides` и `put_Sides` для PolyCtl.cpp на следующий:

    [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]

`get_Sides` Метод возвращает текущее значение `Sides` свойства с помощью `pVal` указатель. В `put_Sides` метод, код обеспечивает пользователю `Sides` свойство допустимым значением. Минимальное значение должно быть 3, а поскольку массив точек будет использоваться для каждой стороны, 100 приемлемого предела для максимального значения.

Теперь у вас есть свойство с именем `Sides`. На следующем шаге мы изменим код прорисовки для его использования.

[Вернитесь к шагу 2](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [к шагу 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)

## <a name="see-also"></a>См. также

[Учебник](../atl/active-template-library-atl-tutorial.md)
