---
title: Изменение кода отрисовки (учебник ATL, часть 4)
ms.custom: get-started-article
ms.date: 09/26/2018
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
ms.openlocfilehash: 6ea7a0ae0c0a9be87fe507e6b934bd046c9ffe4e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295868"
---
# <a name="changing-the-drawing-code-atl-tutorial-part-4"></a>Изменение кода отрисовки (учебник ATL, часть 4)

По умолчанию код рисования элемента управления отображаются квадрата и текст **PolyCtl**. На этом шаге будет изменить код, чтобы отобразить нечто более интересное. Участвуют следующие задачи:

- Изменение файла заголовка

- Изменение `OnDraw` функции

- Добавление метода для вычисления точек многоугольника

- Инициализация цвет заливки

## <a name="modifying-the-header-file"></a>Изменение файла заголовка

Начните с добавления поддержки для функций математической `sin` и `cos`, который будет использоваться вычисления точек многоугольника и путем создания массива для хранения помещает.

### <a name="to-modify-the-header-file"></a>Чтобы изменить файл заголовка

1. Добавьте строку `#include <math.h>` в верхнюю часть PolyCtl.h. В начало файла должно выглядеть следующим образом:

    [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]

1. Реализуйте `IProvideClassInfo` интерфейс, чтобы предоставить сведения о методе для элемента управления, добавив следующий код в PolyCtl.h. В `CPolyCtl` класса, замените строку:

    ```cpp
    public CComControl<CPolyCtl>
    ```

    на

    ```cpp
    public CComControl<CPolyCtl>,
    public IProvideClassInfo2Impl<&CLSID_PolyCtl, &DIID__IPolyCtlEvents, &LIBID_PolygonLib>
    ```

    и в `BEGIN_COM_MAP(CPolyCtl)`, добавьте строки:

    ```cpp
    COM_INTERFACE_ENTRY(IProvideClassInfo)
    COM_INTERFACE_ENTRY(IProvideClassInfo2)
    ```

1. После точки многоугольника вычисляются, они будут храниться в массиве типа `POINT`, поэтому добавьте массива после инструкции определения `short m_nSides;` в PolyCtl.h:

    [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_2.h)]

## <a name="modifying-the-ondraw-method"></a>Изменение метода OnDraw

Теперь следует изменить `OnDraw` метод в PolyCtl.h. Вы добавите код создает нового пера и кисть для рисования вашей многоугольника, а затем вызывает `Ellipse` и `Polygon` функции Win32 API для выполнения фактического рисования.

### <a name="to-modify-the-ondraw-function"></a>Чтобы изменить функцию OnDraw

1. Замените существующий `OnDraw` метод в PolyCtl.h следующим кодом:

    [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]

## <a name="adding-a-method-to-calculate-the-polygon-points"></a>Добавление метода для вычисления точек многоугольника

Добавьте метод с именем `CalcPoints`, вычисляющая координаты точки, составляющие периметра многоугольника. Эти вычисления будет основываться на переменной RECT, который передается в функцию.

### <a name="to-add-the-calcpoints-method"></a>Чтобы добавить метод CalcPoints

1. Добавьте объявление `CalcPoints` для `IPolyCtl` общий раздел `CPolyCtl` классов в PolyCtl.h:

    [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_4.h)]

    Последняя часть общем разделе класса `CPolyCtl` класса будет выглядеть следующим образом:

    [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_5.h)]

1. Добавление этой реализации `CalcPoints` функцию в конец PolyCtl.cpp:

    [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]

## <a name="initializing-the-fill-color"></a>Инициализация цвет заливки

Инициализировать `m_clrFillColor` цветом по умолчанию.

### <a name="to-initialize-the-fill-color"></a>Для инициализации цвет заливки

1. Служит зеленый цвет по умолчанию, добавив следующую строку в `CPolyCtl` конструктор в PolyCtl.h:

    [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_7.h)]

Конструктор теперь выглядит следующим образом:

[!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_8.h)]

## <a name="building-and-testing-the-control"></a>Построение и тестирование элемента управления

Перестройте элемента управления. Убедитесь, что файл PolyCtl.htm закрывается, если она по-прежнему открыта и нажмите кнопку **собрать полигон** на **построения** меню. Можно просмотреть элемент управления еще раз на странице PolyCtl.htm, но на этот раз используйте тестовый контейнер элементов управления ActiveX.

### <a name="to-use-the-activex-control-test-container"></a>Использование тестового контейнера элемента управления ActiveX

1. Создать и запустить тестовый контейнер элементов управления ActiveX. [TSTCON образца: Тестовый контейнер элементов управления ActiveX](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/ole/TstCon) можно найти на сайте GitHub.

    > [!NOTE]
    > Для ошибки, связанные с `ATL::CW2AEX`, в Script.Cpp, замените строку `TRACE( "XActiveScriptSite::GetItemInfo( %s )\n", pszNameT );` с `TRACE( "XActiveScriptSite::GetItemInfo( %s )\n", pszNameT.m_psz );`и строка `TRACE( "Source Text: %s\n", COLE2CT( bstrSourceLineText ) );` с `TRACE( "Source Text: %s\n", bstrSourceLineText );`.<br/>
    > Для ошибки, связанные с `HMONITOR`, откройте файл StdAfx.h в `TCProps` проекта и замените:
    > ```
    > #ifndef WINVER
    > #define WINVER 0x0400
    > #endif
    > ```
    > на
    > ```
    > #ifndef WINVER
    > #define WINVER 0x0500
    > #define _WIN32_WINNT 0x0500
    > #endif
    > ```

1. В **тестовый контейнер**на **изменить** меню, щелкните **вставить новый элемент управления**.

1. Найдите элемент управления, который будет вызываться `PolyCtl class`и нажмите кнопку **ОК**. Вы увидите зеленый треугольник внутри круга.

Попробуйте изменить число сторон, выполнив следующую процедуру. Для изменения свойств на сдвоенный интерфейс изнутри **тестовый контейнер**, использовать **вызов методов**.

### <a name="to-modify-a-controls-property-from-within-the-test-container"></a>Чтобы изменить свойства элемента управления из контейнера теста

1. В **тестовый контейнер**, нажмите кнопку **вызов методов** на **управления** меню.

    **Вызвать метод** диалоговое окно.

1. Выберите **PropPut** версии **сторон** свойства из **имя метода** поле с раскрывающимся списком.

1. Тип `5` в **значение параметра** выберите **задание значения**и нажмите кнопку **Invoke**.

Обратите внимание на то, что элемент управления не изменяется. Несмотря на то, что внутренним образом изменить число сторон, присвоив `m_nSides` переменной, это не вызывает перерисовку элемента управления. При переключении на другое приложение, а затем переключитесь обратно в **тестовый контейнер**, обнаружится, что элемент управления перерисована и имеет правильное число сторон.

Чтобы устранить эту проблему, добавьте вызов `FireViewChange` функции, определенной в `IViewObjectExImpl`, задав число его сторон. Если элемент управления работает в отдельном окне `FireViewChange` вызовет `InvalidateRect` метод напрямую. Если элемент управления работает без окон, `InvalidateRect` метод будет вызван в интерфейс веб-узла контейнера. Это заставляет элемент управления, окрашивание.

### <a name="to-add-a-call-to-fireviewchange"></a>Чтобы добавить вызов FireViewChange

1. Обновите PolyCtl.cpp, добавив вызов `FireViewChange` для `put_Sides` метод. Когда вы закончите, `put_Sides` метод должен выглядеть следующим образом:

    [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]

После добавления `FireViewChange`, перестроение и попробуйте еще раз в тестовом контейнере элемента управления ActiveX элемент управления. Настоящее время, когда вы измените число сторон и нажмите кнопку `Invoke`, вы должны увидеть немедленно изменить элемент управления.

На следующем шаге вы добавите событие.

[Вернитесь к шагу 3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124; [к шагу 5](../atl/adding-an-event-atl-tutorial-part-5.md)

## <a name="see-also"></a>См. также

[Руководство](../atl/active-template-library-atl-tutorial.md)<br/>
[Тестирование свойств и событий с использованием тестового контейнера](../mfc/testing-properties-and-events-with-test-container.md)
