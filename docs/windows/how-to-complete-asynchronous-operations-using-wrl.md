---
title: "Как: завершение асинхронных операций с использованием WRL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c505c44fe18f75eeb64c6b31ca222405f570761
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-complete-asynchronous-operations-using-wrl"></a>Практическое руководство. Завершение асинхронных операций с использованием WRL
В этом документе показано, как использовать среды выполнения C++ шаблон библиотеки Windows (WRL) для запуска асинхронных операций и выполнения работы при завершении операций.  
  
 Здесь приведено два примера. В первом из них показан запуск и ожидание окончания работы асинхронного таймера. В этом примере при создании объекта таймера задается асинхронное действие. Во втором примере показан запуск рабочего потока в фоновом режиме. В этом примере показано, как работать с методом среды выполнения Windows, который возвращает `IAsyncInfo` интерфейса. [Обратного вызова](../windows/callback-function-windows-runtime-cpp-template-library.md) функция является важной частью обоих примеров, поскольку она позволяет задать обработчик событий для обработки результатов асинхронных операций.  
  
 Более простой пример, который создает экземпляр компонента и извлекает значение свойства, в разделе [как: активация и использование компонента среды выполнения Windows](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
> [!TIP]
>  В этих примерах используются лямбда-выражения для определения обратных вызовов. Можно также использовать объекты функций (функторы), указатели на функции или [std::function](../standard-library/function-class.md) объектов. Дополнительные сведения о лямбда-выражения C++ см. в разделе [лямбда-выражения](../cpp/lambda-expressions-in-cpp.md).  
  
## <a name="example-working-with-a-timer"></a>Пример: работа с таймером  
 Следующие действия запускают асинхронный таймер и ожидают окончания его действия. Далее приведен полный пример.  
  
> [!WARNING]
>  Несмотря на то, что обычно используется библиотека шаблонов C++ среды выполнения Windows в приложении универсальной платформы Windows, в этом примере используется консольное приложение для иллюстрации. Функции, такие как `wprintf_s` недоступны в приложении универсальной платформы Windows. Дополнительные сведения о типах и функции, которые можно использовать в приложении универсальной платформы Windows см. в разделе [функции CRT не поддерживаются с параметром/zw](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) и [приложений Win32 и COM для магазина Windows](http://msdn.microsoft.com/library/windows/apps/br205757.aspx).  
  
1.  Включить (`#include`) все необходимые среды выполнения Windows, библиотека шаблонов C++ среды выполнения Windows или заголовков стандартной библиотеки C++.  
  
     [!code-cpp[wrl-consume-async#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_1.cpp)]  
  
     В файле Windows.System.Threading.h объявлены типы, необходимые для использования асинхронного таймера.  
  
     Рекомендуется использовать директиву `using namespace` в CPP-файле, чтобы сделать код более удобочитаемым.  
  
2.  Инициализирует среду выполнения Windows.  
  
     [!code-cpp[wrl-consume-async#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_2.cpp)]  
  
3.  Создайте фабрику активации для интерфейса `ABI::Windows::System::Threading::IThreadPoolTimer`.  
  
     [!code-cpp[wrl-consume-async#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_3.cpp)]  
  
     Среда выполнения Windows использует полные имена для определения типов. `RuntimeClass_Windows_System_Threading_ThreadPoolTimer` Параметр представляет собой строку, предоставляемые средой выполнения Windows и содержит имя класса необходимая среда выполнения.  
  
4.  Создание [событие](../windows/event-class-windows-runtime-cpp-template-library.md) объект, который синхронизирует обратный вызов таймера с основным приложением.  
  
     [!code-cpp[wrl-consume-async#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  Это событие выполняется только для демонстрации в составе консольного приложения. В этом примере используется объект-событие, чтобы удостовериться, что асинхронная операция окончится до завершения приложения. В большинстве приложений обычно не ожидается выполнение асинхронной операции.  
  
5.  Создайте объект `IThreadPoolTimer`, время действия которого истекает через две секунды. Используйте функцию `Callback` для создания обработчика событий (объект `ABI::Windows::System::Threading::ITimerElapsedHandler`).  
  
     [!code-cpp[wrl-consume-async#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_5.cpp)]  
  
6.  Выведите сообщение в окно консоли и дождитесь выполнения обратного вызова таймера. Все объекты `ComPtr` и RAII покидают область действия и автоматически освобождаются.  
  
     [!code-cpp[wrl-consume-async#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_6.cpp)]  
  
 Ниже приведен полный пример.  
  
 [!code-cpp[wrl-consume-async#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_7.cpp)]  
  
### <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или в файл с именем `wrl-consume-async.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe wrl-consume-async.cpp runtimeobject.lib**  
  
## <a name="example-working-with-a-background-thread"></a>Пример: работа с фоновым потоком  
 Следующие действия запускают рабочий поток и определяют действие, которое выполняется этим потоком. Далее приведен полный пример.  
  
> [!TIP]
>  В этом примере показано, как работать с интерфейсом `ABI::Windows::Foundation::IAsyncAction`. Можно применить этот шаблон к любому интерфейсу, реализующему `IAsyncInfo`: `IAsyncAction`, `IAsyncActionWithProgress`, `IAsyncOperation` и `IAsyncOperationWithProgress`.  
  
1.  Включить (`#include`) все необходимые среды выполнения Windows, библиотека шаблонов C++ среды выполнения Windows или заголовков стандартной библиотеки C++.  
  
     [!code-cpp[wrl-consume-asyncOp#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_8.cpp)]  
  
     В файле Windows.System.Threading.h объявлены типы, необходимые для использования рабочего потока.  
  
     Рекомендуется использовать директиву `using namespace` в CPP-файле, чтобы сделать код более удобочитаемым.  
  
2.  Инициализирует среду выполнения Windows.  
  
     [!code-cpp[wrl-consume-asyncOp#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_9.cpp)]  
  
3.  Создайте фабрику активации для интерфейса `ABI::Windows::System::Threading::IThreadPoolStatics`.  
  
     [!code-cpp[wrl-consume-asyncOp#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_10.cpp)]  
  
4.  Создание [событие](../windows/event-class-windows-runtime-cpp-template-library.md) объект, который синхронизирует завершение рабочего потока с основным приложением.  
  
     [!code-cpp[wrl-consume-asyncOp#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_11.cpp)]  
  
    > [!NOTE]
    >  Это событие выполняется только для демонстрации в составе консольного приложения. В этом примере используется объект-событие, чтобы удостовериться, что асинхронная операция окончится до завершения приложения. В большинстве приложений обычно не ожидается выполнение асинхронной операции.  
  
5.  Вызовите метод `IThreadPoolStatics::RunAsync` для создания рабочего потока. Используйте функцию `Callback`для определения действия.  
  
     [!code-cpp[wrl-consume-asyncOp#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_12.cpp)]  
  
     Функция `IsPrime` определена в следующем полном примере.  
  
6.  Выведите сообщение в окно консоли и дождитесь выполнения потока. Все объекты `ComPtr` и RAII покидают область действия и автоматически освобождаются.  
  
     [!code-cpp[wrl-consume-asyncOp#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_13.cpp)]  
  
 Ниже приведен полный пример.  
  
 [!code-cpp[wrl-consume-asyncOp#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_14.cpp)]  
  
### <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или в файл с именем `wrl-consume-asyncOp.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe wrl-consume-asyncOp.cpp runtimeobject.lib**  
  
## <a name="see-also"></a>См. также  
 [Библиотека шаблонов C++ среды выполнения Windows (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)
