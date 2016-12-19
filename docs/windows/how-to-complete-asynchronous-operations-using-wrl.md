---
title: "Практическое руководство. Завершение асинхронных операций с использованием WRL | Microsoft Docs"
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
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Завершение асинхронных операций с использованием WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот документ показывает использование [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) для запуска асинхронных операций и выполнения работы при завершении операций.  
  
 В этом документе показано два примера.  Первый пример запускает асинхронный таймер и ожидает окончания таймера.  В этом примере при создании объекта таймера указывается асинхронное действие.  Во втором примере выполняется фоновый рабочий поток.  В этом примере показано, как работать с методом [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], который возвращает интерфейс `IAsyncInfo`.  Функция [Обратный вызов](../windows/callback-function-windows-runtime-cpp-template-library.md) является важной частью обоих примеров, так как она позволяет определить обработчик событий для обработки результатов асинхронных операций.  
  
 Для более базового примера, который создает экземпляр этого компонента и получает значение свойства, см. [Практическое руководство. Активация и использование компонента среды выполнения Windows](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
> [!TIP]
>  В этих примерах используйте лямбда\-выражения для определения обратных вызовов.  Можно также использовать объекты функций \(функторы\), указатели на функции или объекты [std::function](../standard-library/function-class.md).  Дополнительные сведения о лямбда\-выражениях в C\+\+ см. в разделе [Лямбда\-выражения](../cpp/lambda-expressions-in-cpp.md).  
  
## Пример: Работа с таймером  
 Следующие действия запускают асинхронный таймер и ожидают окончания действия таймера.  Полный пример кода выглядит следующим образом.  
  
> [!WARNING]
>  Хотя обычно используется [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] в приложении [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], в этом образце для иллюстрации используется консольное приложение.  Функции, такие как `wprintf_s`, недоступны из приложения [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о типах и функциях, которые можно использовать в приложении [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] см. [Функции CRT, не поддерживаемые \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) и [Win32 и модели COM для приложений Магазина Windows](http://msdn.microsoft.com/library/windows/apps/br205757.aspx).  
  
1.  Включите \(`#include`\) все необходимые заголовки [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] или стандартной библиотеки C\+\+.  
  
     [!code-cpp[wrl-consume-async#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_1.cpp)]  
  
     Windows.System.Threading.h объявляет типы, необходимые для использования асинхронного таймера.  
  
     Рекомендуется использовать директиву `using namespace` в CPP\-файле, чтобы сделать код более удобочитаемым.  
  
2.  Инициализируйте [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
     [!code-cpp[wrl-consume-async#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_2.cpp)]  
  
3.  Создание фабрики активации для интерфейса `ABI::Windows::System::Threading::IThreadPoolTimer`.  
  
     [!code-cpp[wrl-consume-async#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_3.cpp)]  
  
     В [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] используются полные имена для идентификации типов.  Параметр `RuntimeClass_Windows_System_Threading_ThreadPoolTimer` является строкой, предоставляемой [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], которая содержит требуемое имя класса среды выполнения.  
  
4.  Создайте объект [Событие](../windows/event-class-windows-runtime-cpp-template-library.md), который синхронизирует обратный вызов таймера с основным приложением.  
  
     [!code-cpp[wrl-consume-async#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  Это событие только для демонстрации в составе консольного приложения.  В этом примере используется событие, чтобы гарантировать, что асинхронная операция окончится до завершения приложения.  В большинстве приложений обычно не ожидается выполнение асинхронной операции.  
  
5.  Создайте объект `IThreadPoolTimer`, который истекает через две секунды.  Используйте функцию `Callback` для создания обработчика событий \(объект `ABI::Windows::System::Threading::ITimerElapsedHandler`\).  
  
     [!code-cpp[wrl-consume-async#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_5.cpp)]  
  
6.  Выведите сообщение на консоль и дождитесь выполнения обратного вызова таймера.  Все объекты `ComPtr` и RAII покидают область действия и автоматически освобождаются.  
  
     [!code-cpp[wrl-consume-async#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_6.cpp)]  
  
 Ниже приведен полный пример.  
  
 [!code-cpp[wrl-consume-async#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_7.cpp)]  
  
### Компиляция кода  
 Чтобы скомпилировать код, скопируйте и вставьте его в проект Visual Studio или в файл с именем `wrl-consume-async.cpp`, а затем выполните в окне командной строки Visual Studio следующую команду.  
  
 **cl.exe wrl\-consume\-async.cpp runtimeobject.lib**  
  
## Пример: Работа с фоновым потоком  
 Следующие действия запускают рабочий поток и определяют действие, которое выполняется этим потоком.  Полный пример кода выглядит следующим образом.  
  
> [!TIP]
>  В этом примере показано, как работать с интерфейсом `ABI::Windows::Foundation::IAsyncAction`.  Можно применить этот шаблон к любому интерфейсу, реализующему `IAsyncInfo`: `IAsyncAction`, `IAsyncActionWithProgress`, `IAsyncOperation` и `IAsyncOperationWithProgress`.  
  
1.  Включите \(`#include`\) все необходимые заголовки [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] или стандартной библиотеки C\+\+.  
  
     [!code-cpp[wrl-consume-asyncOp#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_8.cpp)]  
  
     Windows.System.Threading.h объявляет типы, необходимые для использования рабочего потока.  
  
     Рекомендуется использовать директиву `using namespace` в .cpp\-файле, чтобы сделать код более удобочитаемым.  
  
2.  Инициализируйте [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
     [!code-cpp[wrl-consume-asyncOp#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_9.cpp)]  
  
3.  Создание фабрики активации для интерфейса `ABI::Windows::System::Threading::IThreadPoolStatics`.  
  
     [!code-cpp[wrl-consume-asyncOp#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_10.cpp)]  
  
4.  Создайте объект [Событие](../windows/event-class-windows-runtime-cpp-template-library.md), который синхронизирует завершение рабочего потока с основным приложением.  
  
     [!code-cpp[wrl-consume-asyncOp#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_11.cpp)]  
  
    > [!NOTE]
    >  Это событие только для демонстрации в составе консольного приложения.  В этом примере используется событие, чтобы гарантировать, что асинхронная операция окончится до завершения приложения.  В большинстве приложений обычно не ожидается выполнение асинхронной операции.  
  
5.  Вызовите метод `IThreadPoolStatics::RunAsync` для создания рабочего потока.  Используйте функцию `Callback` для задания действия.  
  
     [!code-cpp[wrl-consume-asyncOp#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_12.cpp)]  
  
     Функция `IsPrime` определена в следующем полном примере.  
  
6.  Выведите сообщение на консоль и дождитесь выполнения потока.  Все объекты `ComPtr` и RAII покидают область действия и автоматически освобождаются.  
  
     [!code-cpp[wrl-consume-asyncOp#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_13.cpp)]  
  
 Ниже приведен полный пример.  
  
 [!code-cpp[wrl-consume-asyncOp#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_14.cpp)]  
  
### Компиляция кода  
 Чтобы скомпилировать код, скопируйте и вставьте его в проект Visual Studio или в файл с именем `wrl-consume-asyncOp.cpp`, а затем выполните в окне командной строки Visual Studio следующую команду.  
  
 **cl.exe wrl\-consume\-asyncOp.cpp runtimeobject.lib**  
  
## См. также  
 [Библиотека шаблонов C\+\+ среды выполнения Windows \(WRL\)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)