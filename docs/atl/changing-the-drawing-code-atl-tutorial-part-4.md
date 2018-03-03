---
title: "Изменение кода отрисовки (учебник ATL, часть 4) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ccbf7dab7d39a80efa2b0b0b88b615c55cd9e56d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="changing-the-drawing-code-atl-tutorial-part-4"></a>Изменение кода отрисовки (учебник ATL, часть 4)
По умолчанию отображается код прорисовки элемента управления квадрате и текст **PolyCtl**. На этом шаге будет изменить код, чтобы показать, что-нибудь более интересным. Участвуют следующие задачи:  
  
-   Изменение файла заголовка  
  
-   Изменение `OnDraw` функции  
  
-   Добавление метода для вычисления точек многоугольника  
  
-   Инициализация цвет заливки  
  
## <a name="modifying-the-header-file"></a>Изменение файла заголовка  
 Начните с добавления поддержки для функций математической `sin` и `cos`, который будет использоваться вычисления точек многоугольника и создав массив для хранения помещает.  
  
#### <a name="to-modify-the-header-file"></a>Чтобы изменить файл заголовка  
  
1.  Добавьте строку `#include <math.h>` в верхнюю часть PolyCtl.h. Начало файла должно выглядеть следующим образом:  
  
     [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]  
  
2.  После точки многоугольника вычисляются, они будут сохранены в массив типа `POINT`, поэтому добавьте массива после определения `m_nSides` в PolyCtl.h:  
  
     [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_2.h)]  
  
## <a name="modifying-the-ondraw-method"></a>Изменение OnDraw-метод  
 Теперь следует изменить `OnDraw` метод в PolyCtl.h. Вы добавите код создает новый перо и кисть для отрисовки вашей многоугольника, а затем вызывает `Ellipse` и `Polygon` функции Win32 API для выполнения фактического рисования.  
  
#### <a name="to-modify-the-ondraw-function"></a>Чтобы изменить функцию OnDraw  
  
1.  Заменить существующий `OnDraw` метод PolyCtl.h следующим кодом:  
  
     [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]  
  
## <a name="adding-a-method-to-calculate-the-polygon-points"></a>Добавление метода для вычисления точек многоугольника  
 Добавьте метод с именем `CalcPoints`, вычисляющая координаты точек, которые составляют периметр многоугольника. Эти расчеты будет основываться на RECT переменную, которая передается в функцию.  
  
#### <a name="to-add-the-calcpoints-method"></a>Чтобы добавить метод CalcPoints  
  
1.  Добавьте объявление `CalcPoints` для `IPolyCtl` общий раздел `CPolyCtl` класса в PolyCtl.h:  
  
     [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_4.h)]  
  
     Последняя часть открытого раздел `CPolyCtl` класса будет выглядеть следующим образом:  
  
     [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_5.h)]  
  
2.  Добавление этой реализации `CalcPoints` функции до конца PolyCtl.cpp:  
  
     [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]  
  
## <a name="initializing-the-fill-color"></a>Инициализация цвет заливки  
 Инициализация `m_clrFillColor` цветом по умолчанию.  
  
#### <a name="to-initialize-the-fill-color"></a>Для инициализации цвет заливки  
  
1.  Используйте зеленый цвет по умолчанию, добавив эту строку, чтобы `CPolyCtl` конструктор в PolyCtl.h:  
  
     [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_7.h)]  
  
 Конструктор теперь выглядит следующим образом:  
  
 [!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_8.h)]  
  
## <a name="building-and-testing-the-control"></a>Построение и тестирование элемента управления  
 Перестройте элемента управления. Убедитесь, что файл PolyCtl.htm файл закрывается, если она все еще открыта и нажмите кнопку **построения многоугольника** на **построения** меню. Можно просмотреть элемент управления еще раз на странице файл PolyCtl.htm, но на этот раз используйте тестовый контейнер элемента управления ActiveX.  
  
#### <a name="to-use-the-activex-control-test-container"></a>Использование тестового контейнера элемента управления ActiveX  
  
1.  Постройте и запустите тестовый контейнер элемента управления ActiveX. Дополнительные сведения см. в разделе [образца TSTCON: контейнер для проверки элементов ActiveX](../visual-cpp-samples.md).  
  
2.  В тестовом контейнере на **изменить** меню, нажмите кнопку **вставить новый элемент управления**.  
  
3.  Найдите элемент управления, который будет вызываться `PolyCtl Class`и нажмите кнопку **ОК**. Вы увидите зеленый треугольник внутри круга.  
  
 Попробуйте изменить число сторон, с помощью следующей процедуры. Чтобы изменить свойства сдвоенный интерфейс из тестового контейнера, используйте **вызов методов**.  
  
#### <a name="to-modify-a-controls-property-from-within-the-test-container"></a>Чтобы изменить свойство элемента управления из контейнера тестов  
  
1.  В тестовом контейнере щелкните **вызов методов** на **управления** меню.  
  
     **Вызвать метод** диалоговое окно.  
  
2.  Выберите **PropPut** версии **сторон** свойство из **имя метода** раскрывающегося списка.  
  
3.  Тип `5` в **значение параметра** щелкните **задание значения**и нажмите кнопку **Invoke**.  
  
 Обратите внимание, что элемент управления не изменяется. Несмотря на то, что внутренним образом изменить число сторон, задав `m_nSides` переменной, это не приводит к перерисовку элемента управления. При переходе в другое приложение и затем переключитесь обратно в тестовом контейнере, вы обнаружите, что элемент управления окрашивание и имеет правильное количество сторон.  
  
 Чтобы устранить эту проблему, добавьте вызов `FireViewChange` функции, определенные в `IViewObjectExImpl`, задав число сторон. Если элемент управления работает в собственном окне `FireViewChange` вызовет `InvalidateRect` метод непосредственно. Если элемент управления работает без окон, `InvalidateRect` будет вызван метод интерфейса узла контейнера. Это заставляет элемент управления окрашивание.  
  
#### <a name="to-add-a-call-to-fireviewchange"></a>Чтобы добавить вызов FireViewChange  
  
1.  Обновить, добавив вызов PolyCtl.cpp `FireViewChange` для `put_Sides` метод. После завершения `put_Sides` метод должен выглядеть следующим образом:  
  
     [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]  
  
 После добавления `FireViewChange`, перестроение и повторите попытку в тестовом контейнере элемента управления ActiveX элемента управления. Это время изменить число сторон при нажатии `Invoke`, вы увидите изменение немедленно элемента управления.  
  
 На следующем шаге вы добавите событие.  
  
 [Вернитесь к шагу 3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124; [На шаге 5](../atl/adding-an-event-atl-tutorial-part-5.md)  
  
## <a name="see-also"></a>См. также  
 [Учебник](../atl/active-template-library-atl-tutorial.md)   
 [Тестирование свойств и событий с использованием тестового контейнера](../mfc/testing-properties-and-events-with-test-container.md)

