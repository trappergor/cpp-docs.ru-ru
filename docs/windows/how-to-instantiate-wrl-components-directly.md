---
title: "Как: непосредственно создать экземпляр компонентов WRL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2d307304c103b62ff5ba20e1af25797745bd035
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-instantiate-wrl-components-directly"></a>Практическое руководство. Непосредственное создание экземпляра компонентов WRL
Использование среды выполнения C++ шаблон библиотеки Windows (WRL)[Microsoft::wrl:: make](../windows/make-function.md) и [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) функции для создания экземпляра компонента из модуля, оно определено.  
  
 С помощью создания компонентов напрямую можно уменьшить нагрузку, когда нет необходимости использовать фабрики классов или другие механизмы. Можно создавать компонент непосредственно в обоих приложений универсальной платформы Windows и в приложениях для настольных систем.  
  
 Чтобы узнать, как использовать библиотека шаблонов C++ среды выполнения Windows для создания базового компонента среды выполнения Windows и создать его экземпляр из внешнего приложения универсальной платформы Windows, см. [Пошаговое руководство: создание основного компонента среды выполнения Windows](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md). Сведения об использовании библиотека шаблонов C++ среды выполнения Windows для создания классических компонентов COM и создать его экземпляр из внешнего приложения рабочего стола, в разделе [как: создание классического компонента COM](../windows/how-to-create-a-classic-com-component-using-wrl.md).  
  
 Здесь приведено два примера. В первом примере используется функция `Make` для создания экземпляра компонента. Во втором примере для создания компонента, который может создать ошибку во время построения, используется функция `MakeAndInitialize`. (Поскольку модель COM обычно использует значения `HRESULT` вместо исключений, чтобы показать ошибки, тип модели COM обычно не вызывает исключения из своего конструктора. Функция `MakeAndInitialize` позволяет компоненту проверить его аргументы построения с помощью метода `RuntimeClassInitialize`). Оба примера определяют базовый интерфейс ведения журнала и реализуют этот интерфейс, определяя класс, который выводит сообщения в окно консоли.  
  
> [!IMPORTANT]
>  Нельзя использовать `new` оператор для создания экземпляров компонентов библиотека шаблонов C++ среды выполнения Windows. Поэтому всегда рекомендуется использовать функцию `Make` или `MakeAndInitialize`, чтобы создать компонент напрямую.  
  
### <a name="to-create-and-instantiate-a-basic-logger-component"></a>Создание базового компонента средства ведения журнала и его экземпляров  
  
1.  В Visual Studio создайте **консольное приложение Win32** проекта. Задайте имя проекта, например, `WRLLogger`.  
  
2.  Добавить **Midl файл (.idl)** в проект файл, введите имя файла `ILogger.idl`, а затем добавьте следующий код:  
  
     [!code-cpp[wrl-logger-make#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]  
  
3.  Замените содержимое файла WRLLogger.cpp следующим кодом:  
  
     [!code-cpp[wrl-logger-make#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]  
  
### <a name="to-handle-construction-failure-for-the-basic-logger-component"></a>Обработка сбоя построения для базового компонента средства ведения журнала  
  
1.  Замените определение класса `CConsoleWriter` следующим кодом: Эта версия содержит частную строковую переменную-член и переопределяет метод `RuntimeClass::RuntimeClassInitialize`. Метод `RuntimeClassInitialize` завершается неудачей, если вызов `SHStrDup` завершается неудачей.  
  
     [!code-cpp[wrl-logger-makeandinitialize#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]  
  
2.  Замените `wmain` следующим кодом: Эта версия использует метод `MakeAndInitialize` для создания экземпляра объекта `CConsoleWriter` и проверяет результат `HRESULT`.  
  
     [!code-cpp[wrl-logger-makeandinitialize#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Библиотека шаблонов C++ среды выполнения Windows (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Microsoft::wrl:: make](../windows/make-function.md)   
 [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md)