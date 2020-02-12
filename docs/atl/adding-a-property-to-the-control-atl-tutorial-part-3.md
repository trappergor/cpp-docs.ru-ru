---
title: Добавление свойства в элемент управления (учебник ATL, часть 3)
ms.custom: get-started-article
ms.date: 09/26/2018
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
ms.openlocfilehash: 288dc9f5af57c02639d15a9a971419a633cfc08d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127591"
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>Добавление свойства в элемент управления (учебник ATL, часть 3)

`IPolyCtl` — это интерфейс, который содержит пользовательские методы и свойства элемента управления, и в него добавляется свойство.

### <a name="to-add-the-property-definitions-to-your-project"></a>Добавление определений свойств в проект

1. В **представление классов**разверните ветвь `Polygon`.

1. Щелкните правой кнопкой мыши `IPolyCtl`.

1. В контекстном меню выберите команду **Добавить**, а затем щелкните **Добавить свойство**. Появится мастер **добавления свойств** .

1. В качестве **имени свойства**введите `Sides`.

1. В раскрывающемся списке **тип свойства**выберите `short`.

1. Нажмите кнопку **ОК** , чтобы завершить добавление свойства.

1. В **Обозреватель решений**откройте Polygon. idl и замените следующие строки в конце интерфейса `IPolyCtl : IDispatch`:

    ```cpp
    short get_Sides();
    void set_Sides(short value);
    ```

    на

    ```cpp
    [propget, id(1), helpstring("property Sides")] HRESULT Sides([out, retval] short *pVal);
    [propput, id(1), helpstring("property Sides")] HRESULT Sides([in] short newVal);
    ```

1. В **Обозреватель решений**откройте поликтл. h и добавьте следующие строки после определения `m_clrFillColor`:

    [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]

Хотя теперь у вас есть скелет функций для установки и извлечения свойства и переменной для хранения свойства, необходимо реализовать соответствующие функции.

### <a name="to-update-the-get-and-put-methods"></a>Обновление методов Get и WHERE

1. Задайте значение по умолчанию для `m_nSides`. Сделайте фигуру по умолчанию треугольником, добавив строку в конструктор в Поликтл. h:

    [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]

1. Реализуйте методы `Get` и `Put`. Объявления функций `get_Sides` и `put_Sides` были добавлены в Поликтл. h. Теперь добавьте код для `get_Sides` и `put_Sides` в Поликтл. cpp следующим образом:

    [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]

Метод `get_Sides` возвращает текущее значение свойства `Sides` через указатель `pVal`. В методе `put_Sides` код позволяет пользователю задать для свойства `Sides` допустимое значение. Минимальное значение должно быть 3, а поскольку массив точек будет использоваться для каждой стороны, 100 является разумным ограничением для максимального значения.

Теперь у вас есть свойство с именем `Sides`. На следующем шаге вы измените код рисования, чтобы он использовался.

[Вернитесь к шагу 2](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [на шаге 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) .

## <a name="see-also"></a>См. также раздел

[Руководство](../atl/active-template-library-atl-tutorial.md)
