---
title: Как выполнить Обработка событий с помощью WRL
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
ms.openlocfilehash: 35c806660c18ad234f37dba92780b7633e032644
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336568"
---
# <a name="how-to-handle-events-using-wrl"></a>Как выполнить Обработка событий с помощью WRL

В этом документе демонстрируется использование Windows шаблонов среды выполнения C++ Library (WRL) и обрабатывать события объекта среды выполнения Windows.

Более простой пример, который создает экземпляр этого компонента и извлекает значение свойства, см. в разделе [как: Активация и использование компонента среды выполнения Windows](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).

## <a name="subscribing-to-and-handling-events"></a>Подписка на события и их обработка

Следующие действия запускают объект `ABI::Windows::System::Threading::IDeviceWatcher` и используют обработчики событий для отслеживания прогресса. Интерфейс `IDeviceWatcher` позволяет перечислять устройства асинхронно (или в фоновом режиме) и получать уведомление при добавлении, удалении и изменении устройства. [Обратного вызова](callback-function-wrl.md) функция является важной частью в этом примере, поскольку она позволяет определить обработчики событий, которые обрабатывают результаты фоновых операций. Полный пример выглядит следующим образом.

> [!WARNING]
> Несмотря на то, что обычно используется библиотека шаблонов C++ среды выполнения Windows в приложении универсальной платформы Windows, в этом примере используется консольное приложение для иллюстрации. Функции, такие как `wprintf_s` не доступны из приложения универсальной платформы Windows. Дополнительные сведения о типах и функциях, которые можно использовать в приложении универсальной платформы Windows, см. в разделе [функции CRT не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) и [Win32 и COM для приложений UWP](/uwp/win32-and-com/win32-and-com-for-uwp-apps).

1. Включить (`#include`) все необходимые заголовки стандартной библиотеки C++, библиотека шаблонов C++ среды выполнения Windows или среды выполнения Windows.

   [!code-cpp[wrl-consume-event#2](../codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]

   `Windows.Devices.Enumeration.h` Объявляет типы, которые требуются для перечисления устройств.

   Рекомендуется использовать директиву `using namespace` в CPP-файле, чтобы сделать код более удобочитаемым.

2. Объявите локальные переменные для приложения. Этот пример проводит подсчет количества перечисленных устройств и токенов регистрации, которые позволяют в дальнейшем отменять подписку на события.

   [!code-cpp[wrl-consume-event#7](../codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]

3. Инициализации среды выполнения Windows.

   [!code-cpp[wrl-consume-event#3](../codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]

4. Создание [событие](event-class-wrl.md) объект, который синхронизирует завершение процесса перечисления с основным приложением.

   [!code-cpp[wrl-consume-event#4](../codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]

   > [!NOTE]
   > Это событие выполняется только для демонстрации в составе консольного приложения. В этом примере используется объект-событие, чтобы удостовериться, что асинхронная операция окончится до завершения приложения. В большинстве приложений обычно не ожидается выполнение асинхронной операции.

5. Создайте фабрику активации для интерфейса `IDeviceWatcher`.

   [!code-cpp[wrl-consume-event#5](../codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]

   Среда выполнения Windows использует полные имена для идентификации типов. `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` Параметр представляет собой строку, которая предоставляется средой выполнения Windows и содержит имя класса необходимая среда выполнения.

6. Создайте объект `IDeviceWatcher`.

   [!code-cpp[wrl-consume-event#6](../codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]

7. Используйте функцию `Callback` для подписки на события `Added`, `EnumerationCompleted` и `Stopped`.

   [!code-cpp[wrl-consume-event#8](../codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]

   Обработчик событий `Added` увеличивает число перечисленных устройств. Он останавливает процесс перечисления после обнаружения десяти устройств.

   Обработчик событий `Stopped` удаляет обработчики событий и задает событие завершения.

   Обработчик событий `EnumerationCompleted` останавливает процесс перечисления. Рекомендуется обрабатывать это событие, если имеется менее десяти устройств.

   > [!TIP]
   > В этом примере используется лямбда-выражение для определения обратных вызовов. Можно также использовать объекты функций (функторы), указатели функций или [std::function](../../standard-library/function-class.md) объектов. Дополнительные сведения о лямбда-выражениях см. в разделе [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md).

8. Запустите процесс перечисления.

   [!code-cpp[wrl-consume-event#9](../codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]

9. Дождитесь завершения процесса перечисления, а затем выведите сообщение. Все объекты `ComPtr` и RAII покидают область действия и автоматически освобождаются.

   [!code-cpp[wrl-consume-event#10](../codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]

Ниже приведен полный пример.

[!code-cpp[wrl-consume-event#1](../codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или вставьте его в файл с именем `wrl-consume-events.cpp` и затем выполните следующую команду **Командная строка Visual Studio** окна.

`cl.exe wrl-consume-events.cpp runtimeobject.lib`

## <a name="see-also"></a>См. также

[Библиотека шаблонов C++ среды выполнения Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)