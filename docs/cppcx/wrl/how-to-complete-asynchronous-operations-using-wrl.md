---
title: Практическое руководство. Завершение асинхронных операций с использованием WRL
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
ms.openlocfilehash: 8e7e52342cf73a56c6c33d4d1f998f446d632ddd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213945"
---
# <a name="how-to-complete-asynchronous-operations-using-wrl"></a>Практическое руководство. Завершение асинхронных операций с использованием WRL

В этом документе показано, как использовать библиотеку C++ шаблонов среда выполнения Windows (WRL) для запуска асинхронных операций и выполнения работы по завершении операций.

Здесь приведено два примера. В первом из них показан запуск и ожидание окончания работы асинхронного таймера. В этом примере при создании объекта таймера задается асинхронное действие. Во втором примере показан запуск рабочего потока в фоновом режиме. В этом примере показано, как работать с среда выполнения Windowsным методом, который возвращает интерфейс `IAsyncInfo`. Функция [обратного вызова](callback-function-wrl.md) является важной частью обоих примеров, поскольку позволяет им указать обработчик событий для обработки результатов асинхронных операций.

Более простой пример, в котором создается экземпляр компонента и извлекается значение свойства, см. в разделе [как активировать и использовать компонент Среда выполнения Windows](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).

> [!TIP]
> В этих примерах используются лямбда-выражения для определения обратных вызовов. Можно также использовать объекты функций (операторов), указатели функций или объекты [std:: Function](../../standard-library/function-class.md) . Дополнительные сведения о C++ лямбда-выражениях см. в разделе [лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md).

## <a name="example-working-with-a-timer"></a>Пример: работа с таймером

Следующие действия запускают асинхронный таймер и ожидают окончания его действия. Полный пример приведен ниже.

> [!WARNING]
> Хотя обычно библиотека шаблонов среда выполнения Windows C++ используется в приложении универсальная платформа Windows (UWP), в этом примере для иллюстрации используется консольное приложение. Такие функции, как `wprintf_s`, недоступны в приложении UWP. Дополнительные сведения о типах и функциях, которые можно использовать в приложении UWP, см. в разделе [функции CRT, которые не поддерживаются в приложениях универсальная платформа Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) и [Win32 и com для приложений UWP](/uwp/win32-and-com/win32-and-com-for-uwp-apps).

1. Включите (`#include`) все необходимые среда выполнения Windows, среда выполнения Windows C++ библиотека шаблонов или C++ заголовки стандартной библиотеки.

   [!code-cpp[wrl-consume-async#2](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_1.cpp)]

   `Windows.System.Threading.h` объявляет типы, необходимые для использования асинхронного таймера.

   Рекомендуется использовать директиву `using namespace` в CPP-файле, чтобы сделать код более удобочитаемым.

2. Инициализируйте среда выполнения Windows.

   [!code-cpp[wrl-consume-async#3](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_2.cpp)]

3. Создайте фабрику активации для интерфейса `ABI::Windows::System::Threading::IThreadPoolTimer`.

   [!code-cpp[wrl-consume-async#4](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_3.cpp)]

   Среда выполнения Windows использует полные имена для указания типов. Параметр `RuntimeClass_Windows_System_Threading_ThreadPoolTimer` — это строка, предоставляемая среда выполнения Windows и содержащая имя требуемого класса среды выполнения.

4. Создайте объект [события](event-class-wrl.md) , который синхронизирует обратный вызов таймера с основным приложением.

   [!code-cpp[wrl-consume-async#5](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_4.cpp)]

   > [!NOTE]
   > Это событие выполняется только для демонстрации в составе консольного приложения. В этом примере используется объект-событие, чтобы удостовериться, что асинхронная операция окончится до завершения приложения. В большинстве приложений обычно не ожидается выполнение асинхронной операции.

5. Создайте объект `IThreadPoolTimer`, время действия которого истекает через две секунды. Используйте функцию `Callback` для создания обработчика событий (объект `ABI::Windows::System::Threading::ITimerElapsedHandler`).

   [!code-cpp[wrl-consume-async#6](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_5.cpp)]

6. Выведите сообщение в окно консоли и дождитесь выполнения обратного вызова таймера. Все объекты `ComPtr` и RAII покидают область действия и автоматически освобождаются.

   [!code-cpp[wrl-consume-async#7](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_6.cpp)]

Ниже приведен полный пример.

[!code-cpp[wrl-consume-async#1](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_7.cpp)]

### <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и вставьте в проект Visual Studio или вставьте в файл с именем `wrl-consume-async.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

`cl.exe wrl-consume-async.cpp runtimeobject.lib`

## <a name="example-working-with-a-background-thread"></a>Пример: работа с фоновым потоком

Следующие действия запускают рабочий поток и определяют действие, которое выполняется этим потоком. Полный пример приведен ниже.

> [!TIP]
> В этом примере показано, как работать с интерфейсом `ABI::Windows::Foundation::IAsyncAction`. Можно применить этот шаблон к любому интерфейсу, реализующему `IAsyncInfo`: `IAsyncAction`, `IAsyncActionWithProgress`, `IAsyncOperation` и `IAsyncOperationWithProgress`.

1. Включите (`#include`) все необходимые среда выполнения Windows, среда выполнения Windows C++ библиотека шаблонов или C++ заголовки стандартной библиотеки.

   [!code-cpp[wrl-consume-asyncOp#2](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_8.cpp)]

   В файле Windows.System.Threading.h объявлены типы, необходимые для использования рабочего потока.

   Рекомендуется использовать директиву `using namespace` в CPP-файле, чтобы сделать код более удобочитаемым.

2. Инициализируйте среда выполнения Windows.

   [!code-cpp[wrl-consume-asyncOp#3](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_9.cpp)]

3. Создайте фабрику активации для интерфейса `ABI::Windows::System::Threading::IThreadPoolStatics`.

   [!code-cpp[wrl-consume-asyncOp#4](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_10.cpp)]

4. Создайте объект [события](event-class-wrl.md) , который синхронизирует завершение рабочего потока с основным приложением.

   [!code-cpp[wrl-consume-asyncOp#5](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_11.cpp)]

   > [!NOTE]
   > Это событие выполняется только для демонстрации в составе консольного приложения. В этом примере используется объект-событие, чтобы удостовериться, что асинхронная операция окончится до завершения приложения. В большинстве приложений обычно не ожидается выполнение асинхронной операции.

5. Вызовите метод `IThreadPoolStatics::RunAsync` для создания рабочего потока. Используйте функцию `Callback`для определения действия.

   [!code-cpp[wrl-consume-asyncOp#6](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_12.cpp)]

   Функция `IsPrime` определена в следующем полном примере.

6. Выведите сообщение в окно консоли и дождитесь выполнения потока. Все объекты `ComPtr` и RAII покидают область действия и автоматически освобождаются.

   [!code-cpp[wrl-consume-asyncOp#7](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_13.cpp)]

Ниже приведен полный пример.

[!code-cpp[wrl-consume-asyncOp#1](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_14.cpp)]

### <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и вставьте в проект Visual Studio или вставьте в файл с именем `wrl-consume-asyncOp.cpp` а затем выполните следующую команду в окне **командной строки Visual Studio** .

`cl.exe wrl-consume-asyncOp.cpp runtimeobject.lib`

## <a name="see-also"></a>См. также раздел

[Библиотека шаблонов C++ среды выполнения Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)
