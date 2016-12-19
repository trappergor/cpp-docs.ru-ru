---
title: "Пошаговое руководство. Создание базового компонента среды выполнения Windows с использованием WRL | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 6e3f0986-7905-4f94-90e5-22c2ebfc8cd0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Пошаговое руководство. Создание базового компонента среды выполнения Windows с использованием WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот документ демонстрирует использование [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] ([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]) для создания базового компонента среды выполнения ([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]). Компонент складывает 2 числа и вызывает событие, если результат — простое число. Также в этом документе демонстрируется работа с компонентом из приложения, распространяемого через [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], использующего JavaScript.  
  
## <a name="prerequisites"></a>Предварительные требования  
  
-   Опыт работы с [среды выполнения Windows](http://msdn.microsoft.com/library/windows/apps/br211377.aspx).  
  
-   опыт работы с моделью COM;  
  
### <a name="to-create-a-basic-includewrttokenwrtmdmd-component-that-adds-two-numbers"></a>Создание базового компонента среды выполнения ([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]), который складывает 2 числа  
  
1.  В Visual Studio создайте Visual C++ `WRLClassLibrary` проекта. Документ [шаблон проекта библиотеки классов](../windows/wrl-class-library-project-template.md) описывает, как загрузить этот шаблон. Задайте для проекта имя `Contoso`.  
  
2.  В файлах Contoso.cpp и Contoso.idl замените все вхождения "WinRTClass" на "Calculator".  
  
3.  В файле Contoso.idl добавьте метод `Add` в интерфейс `ICalculator`.  
  
     [!code-cpp[wrl-basic-component#1](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_1.idl)]  
  
4.  В файле Contoso.cpp в секцию `Add` класса `public` добавьте метод `Calculator`.  
  
     [!code-cpp[wrl-basic-component#2](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_2.cpp)]  
  
    > [!IMPORTANT]
    >  Поскольку создается компонент модели COM, необходимо использовать соглашение о вызовах `__stdcall`.  
  
     Рекомендуется использовать `_Out_` и другие заметки на языке заметок к исходному коду (SAL), чтобы описать, как функция использует эти параметры. Заметки на языке SAL также описывают возвращаемые значения. ЭТИ заметки работают с [средство анализа кода C/C++](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md) для обнаружения возможных ошибок в C и C++ в исходном коде. Наиболее распространенные ошибки обнаруживаемые этим инструментом — переполнение буфера, неинициализированная память, разыменование пустых указателей, а также утечка памяти и ресурсов.  
  
### <a name="to-use-the-component-from-a-includewin8appnamelongtokenwin8appnamelongmdmd-app-that-uses-javascript"></a>Работа с компонентом из приложения, распространяемого через [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], использующего JavaScript  
  
1.  В Visual Studio, добавьте новый JavaScript `Blank App` проект `Contoso` решения. Задайте для проекта имя `CalculatorJS`.  
  
2.  В `CalculatorJS` проекта, добавьте ссылку на `Contoso` проекта.  
  
3.  В файле default.html замените раздел `body` этими элементами пользовательского интерфейса:  
  
     [!code-html[wrl-basic-component#3](../windows/codesnippet/Html/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_3.html)]  
  
4.  В файле default.js реализуйте функцию `OnClick`.  
  
     [!code-javascript[wrl-basic-component#4](../windows/codesnippet/JavaScript/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_4.js)]  
  
    > [!NOTE]
    >  В JavaScript имена методов начинаются с буквы в нижнем регистре в соответствии со стандартным положением об именовании.  
  
### <a name="to-add-an-event-that-fires-when-a-prime-number-is-calculated"></a>Добавление события, вызываемого при вычислении простого числа  
  
1.  В файле Contoso.idl перед объявлением `ICalculator` определите тип делегата `PrimeNumberEvent`, который предоставляет аргумент `int`.  
  
     [!code-cpp[wrl-basic-component#5](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_5.idl)]  
  
     Если используется ключевое слово `delegate`, компилятор MIDL создает интерфейс, содержащий метод `Invoke`, который совпадает с сигнатурой этого делегата. В этом примере созданный файл Contoso_h.h определяет интерфейс `IPrimeNumberEvent`, который используется далее в этой процедуре.  
  
     [!code-cpp[wrl-basic-component#13](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_6.cpp)]  
  
2.  В интерфейсе `ICalculator` определите событие `PrimeNumberFound`. Атрибуты `eventadd` и `eventremove` указывают, что объект-получатель интерфейса `ICalculator` может как подписаться, так и отказаться от подписки на это событие.  
  
     [!code-cpp[wrl-basic-component#6](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_7.idl)]  
  
3.  В файле Contoso.cpp добавьте `private` [Microsoft::wrl:: eventsource](../windows/eventsource-class.md) переменную-член для управления подписчиками события и вызова обработчика событий.  
  
     [!code-cpp[wrl-basic-component#7](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_8.cpp)]  
  
4.  В файле Contoso.cpp реализуйте методы `add_PrimeNumberFound` и `remove_PrimeNumberFound`.  
  
     [!code-cpp[wrl-basic-component#8](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_9.cpp)]  
  
### <a name="to-raise-the-event-when-a-prime-number-is-calculated"></a>Вызов события при вычислении простого числа  
  
1.  В файле Contoso.cpp в секцию `IsPrime` класса `private` добавьте метод `Calculator`.  
  
     [!code-cpp[wrl-basic-component#12](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_10.cpp)]  
  
2.  Изменить `Calculator` `Add` метод для вызова [Microsoft::WRL::EventSource::InvokeAll](../windows/eventsource-invokeall-method.md) метод, когда вычисляется простое число.  
  
     [!code-cpp[wrl-basic-component#11](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_11.cpp)]  
  
### <a name="to-handle-the-event-from-javascript"></a>Обработка события в коде JavaScript  
  
1.  В файле default.html измените раздел `body`, чтобы добавить текстовую область, содержащую простые числа.  
  
     [!code-html[wrl-basic-component#9](../windows/codesnippet/Html/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_12.html)]  
  
2.  В файле default.js измените функцию `Add` для обработки события `PrimeNumberFound`. Обработчик события добавляет простое число в текстовую область, определенную на предыдущем шаге.  
  
     [!code-javascript[wrl-basic-component#10](../windows/codesnippet/JavaScript/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_13.js)]  
  
    > [!NOTE]
    >  В JavaScript имена событий начинаются с буквы в нижнем регистре и предваряются текстом "on" в соответствии со стандартным положением об именовании.  
  
 На следующем рисунке показано пример простого приложения "Калькулятор".  
  
 ![Основное приложение "Калькулятор", использующее JavaScript](../windows/media/wrl_basic_component.png "WRL_Basic_Component")  
  
## <a name="next-steps"></a>Дальнейшие действия  
  
## <a name="see-also"></a>См. также  
 [Библиотека шаблонов C++ среды выполнения Windows (WRL)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)   
 [Шаблон проекта библиотеки классов](../windows/wrl-class-library-project-template.md)   
 [Средство анализа кода C/C++](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md)