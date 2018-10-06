---
title: Добавление события (учебник ATL, часть 5) | Документация Майкрософт
ms.custom: get-started-article
ms.date: 09/27/2018
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9cec895019855e2d3744f722bd15ad3a10288597
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821313"
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>Добавление события (учебник ATL, часть 5)

На этом шаге вы добавите `ClickIn` и `ClickOut` событий в элемент управления ATL. Будет срабатывать `ClickIn` событие, если пользователь щелкает внутри многоугольника и fire `ClickOut` при щелчке за пределами. Далее приведены задачи, чтобы добавить событие.

- Добавление `ClickIn` и `ClickOut` методы

- Создание библиотеки типов

- Реализация точки подключения интерфейсов

## <a name="adding-the-clickin-and-clickout-methods"></a>Добавление методов ClickIn и ClickOut

Если элемент управления ATL, созданного на шаге 2, вы выбрали **точек подключения** "флажок". Созданной `_IPolyCtlEvents` интерфейс в файле Polygon.idl. Обратите внимание, что имя интерфейса начинается с символа подчеркивания. Это соглашение, чтобы указать, что интерфейс является внутренний интерфейс. Таким образом программы, которые позволяют просматривать COM-объектов можно не отображать интерфейс для пользователя. Также Обратите внимание, что **точек подключения** добавьте следующую строку в файле Polygon.idl, чтобы указать, что `_IPolyCtlEvents` исходный интерфейс по умолчанию:

`[default, source] dispinterface _IPolyCtlEvents;`

Исходный атрибут указывает элемент управления источник уведомления, поэтому он вызывает этот интерфейс для контейнера.

Теперь добавьте `ClickIn` и `ClickOut` методы `_IPolyCtlEvents` интерфейс.

### <a name="to-add-the-clickin-and-clickout-methods"></a>Добавление методов ClickIn и ClickOut

1. В **обозревателе решений**откройте Polygon.idl и добавьте следующий код под `methods:` в `dispInterface_IPolyCtlEvents` объявление PolygonLib библиотеки:

    ```cpp
   [id(1), helpstring("method ClickIn")] void ClickIn([in] LONG x,[in] LONG y);
   [id(2), helpstring("method ClickOut")] void ClickOut([in] LONG x,[in] LONG y);
    ```

`ClickIn` И `ClickOut` методы принимают x и y координаты выбранной точки в качестве параметров.

## <a name="generating-the-type-library"></a>Создание библиотеки типов

На этом этапе создавайте библиотеку типов, так как проект будет использовать его для получения сведения, необходимые для создания точки подключения интерфейса и интерфейс контейнера точки подключения для элемента управления.

### <a name="to-generate-the-type-library"></a>Для создания библиотеки типов

1. Перестройте проект.

     - или -

1. Щелкните правой кнопкой мыши файл Polygon.idl в **обозревателе решений** и нажмите кнопку **компиляции** в контекстном меню.

Это создаст файл Polygon.tlb, который является библиотека типов. Файл Polygon.tlb не видим за **обозревателе решений**, так как он является двоичным файлом и для просмотра или непосредственного редактирования.

## <a name="implementing-the-connection-point-interfaces"></a>Реализация точки подключения интерфейсов

Реализация точки подключения интерфейса и интерфейс контейнера точки подключения для элемента управления. В модели COM события, реализуются через механизм точек подключения. Для получения событий из COM-объект, контейнер устанавливает вспомогательное соединение в точку подключения, которая реализует COM-объекта. Так как COM-объект может иметь несколько точек подключения, COM-объекта также реализует интерфейс контейнера точки подключения. Через этот интерфейс контейнера можно определить, какие точки подключения поддерживаются.

Интерфейс, который реализует точку соединения вызывается `IConnectionPoint`, и интерфейс, реализующий контейнер точек соединения называется `IConnectionPointContainer`.

Чтобы реализовать `IConnectionPoint`, используется мастер реализации точек подключения. Этот мастер создает `IConnectionPoint` интерфейс путем чтения свою библиотеку типов и реализации функции, для каждого события, которое будет порождено.

### <a name="to-implement-the-connection-points"></a>Для реализации точек подключения

1. В **обозревателе решений**откройте _IPolyCtlEvents_CP.h и добавьте следующий код под `public:` инструкции в `CProxy_IPolyCtlEvents` класса:

    ```cpp
    VOID Fire_ClickIn(LONG x, LONG y)
    {
        T* pT = static_cast<T*>(this);
        int nConnectionIndex;
        CComVariant* pvars = new CComVariant[2];
        int nConnections = m_vec.GetSize();

        for (nConnectionIndex = 0; nConnectionIndex < nConnections; nConnectionIndex++)
        {
            pT->Lock();
            CComPtr<IUnknown> sp = m_vec.GetAt(nConnectionIndex);
            pT->Unlock();
            IDispatch* pDispatch = reinterpret_cast<IDispatch*>(sp.p);
            if (pDispatch != NULL)
            {
                pvars[1].vt = VT_I4;
                pvars[1].lVal = x;
                pvars[0].vt = VT_I4;
                pvars[0].lVal = y;
                DISPPARAMS disp = { pvars, NULL, 2, 0 };
                pDispatch->Invoke(0x1, IID_NULL, LOCALE_USER_DEFAULT, DISPATCH_METHOD, &disp, NULL, NULL, NULL);
            }
        }
        delete[] pvars;

    }
    VOID Fire_ClickOut(LONG x, LONG y)
    {
        T* pT = static_cast<T*>(this);
        int nConnectionIndex;
        CComVariant* pvars = new CComVariant[2];
        int nConnections = m_vec.GetSize();

        for (nConnectionIndex = 0; nConnectionIndex < nConnections; nConnectionIndex++)
        {
            pT->Lock();
            CComPtr<IUnknown> sp = m_vec.GetAt(nConnectionIndex);
            pT->Unlock();
            IDispatch* pDispatch = reinterpret_cast<IDispatch*>(sp.p);
            if (pDispatch != NULL)
            {
                pvars[1].vt = VT_I4;
                pvars[1].lVal = x;
                pvars[0].vt = VT_I4;
                pvars[0].lVal = y;
                DISPPARAMS disp = { pvars, NULL, 2, 0 };
                pDispatch->Invoke(0x2, IID_NULL, LOCALE_USER_DEFAULT, DISPATCH_METHOD, &disp, NULL, NULL, NULL);
            }
        }
        delete[] pvars;

    }
    ```

Вы увидите, что этот файл содержит класс с именем `CProxy_IPolyCtlEvents` , наследуемый от класса `IConnectionPointImpl`. _IPolyCtlEvents_CP.h теперь определяет два метода `Fire_ClickIn` и `Fire_ClickOut`, которое занять два параметра координат. Вызывать эти методы, если вы хотите запустить событие от элемента управления.

Создав элемент управления с **точек подключения** выбранным параметром _IPolyCtlEvents_CP.h файл был создан для вас. Также добавлен `CProxy_PolyEvents` и `IConnectionPointContainerImpl` для нескольких список наследования элемента управления и предоставляются `IConnectionPointContainer` вам, добавив соответствующие записи в сопоставление COM.

Не требуется реализация кода для поддержки событий. Теперь добавьте код, который будет запускать события в соответствующий момент. Помните, что вы собираетесь запускать `ClickIn` или `ClickOut` событие, когда пользователь нажимает кнопку мыши в элементе управления. Чтобы узнать, когда пользователь нажимает кнопку, добавить обработчик для `WM_LBUTTONDOWN` сообщения.

### <a name="to-add-a-handler-for-the-wmlbuttondown-message"></a>Чтобы добавить обработчик для сообщения WM_LBUTTONDOWN

1. В **представление классов**, щелкните правой кнопкой мыши `CPolyCtl` класса и нажмите кнопку **свойства** в контекстном меню.

1. В **свойства** окно, нажмите кнопку **сообщений** значок и нажмите кнопку `WM_LBUTTONDOWN` из списка слева.

1. В появившемся раскрывающемся списке выберите  **\<Добавить > OnLButtonDown**. `OnLButtonDown` Объявление обработчика будут добавляться в PolyCtl.h и PolyCtl.cpp добавляется на реализацию обработчика.

Далее измените обработчик.

### <a name="to-modify-the-onlbuttondown-method"></a>Чтобы изменить OnLButtonDown-метод

1. Измените код, который состоит из `OnLButtonDown` метод в PolyCtl.cpp (удаление любой код, помещенный в мастере), чтобы он выглядел следующим образом:

    [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]

Это делает код, используйте точки вычисляются в `OnDraw` функцию для создания в регион, который обнаруживает щелчки мыши пользователя с помощью вызова `PtInRegion`.

*UMsg* параметр является Идентификатором обрабатываемого сообщения Windows. Это позволяет иметь одну функцию, обрабатывающий ряд сообщений. *WParam* и *lParam* параметры — это стандартные значения для обрабатываемого сообщения. Параметр *bHandled* позволяет указать, обработано ли функция сообщение. По умолчанию оно имеет значение TRUE для указания, что функция обработал сообщение, но его можно задать значение false. В результате ATL продолжать поиск другую функцию обработчика сообщений для отправки сообщения.

## <a name="building-and-testing-the-control"></a>Построение и тестирование элемента управления

Теперь попробуйте событий. Создать элемент управления и снова запустите тестовый контейнер элементов управления ActiveX. На этот раз просмотрите окно "журнал событий". Чтобы перенаправлять события в окне вывода, нажмите кнопку **ведение журнала** из **параметры** меню и выберите **журнала в окне вывода**. Вставьте элемент управления и щелкните в окне. Обратите внимание, что `ClickIn` возникает, если щелкнуть внутри закрашенного многоугольника, и `ClickOut` срабатывает, если щелкнуть вне его.

Далее добавим страницу свойств.

[Вернитесь к шагу 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [к шагу 6](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="see-also"></a>См. также

[Учебник](../atl/active-template-library-atl-tutorial.md)
