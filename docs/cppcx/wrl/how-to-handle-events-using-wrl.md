---
title: Практическое руководство. Обработка событий с использованием WRL
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
ms.openlocfilehash: 0e13212d7cb481bc72a903a31fb170fd1ff8b7ec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213932"
---
# <a name="how-to-handle-events-using-wrl"></a>Практическое руководство. Обработка событий с использованием WRL

В этом документе показано, как использовать библиотеку C++ шаблонов среда выполнения Windows (WRL) для подписки на события объекта среда выполнения Windows и управления им.

Более простой пример, в котором создается экземпляр компонента и извлекается значение свойства, см. в разделе [как активировать и использовать компонент Среда выполнения Windows](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).

## <a name="subscribing-to-and-handling-events"></a>Подписка на события и их обработка

Следующие действия запускают объект `ABI::Windows::System::Threading::IDeviceWatcher` и используют обработчики событий для отслеживания прогресса. Интерфейс `IDeviceWatcher` позволяет перечислять устройства асинхронно (или в фоновом режиме) и получать уведомление при добавлении, удалении и изменении устройства. Функция [обратного вызова](callback-function-wrl.md) является важной частью этого примера, так как она позволяет ей указывать обработчики событий, обрабатывающие результаты фоновой операции. Полный пример приведен ниже.

> [!WARNING]
> Хотя обычно библиотека шаблонов среда выполнения Windows C++ используется в приложении универсальная платформа Windows, в этом примере для иллюстрации используется консольное приложение. Такие функции, как `wprintf_s`, недоступны в приложении универсальная платформа Windows. Дополнительные сведения о типах и функциях, которые можно использовать в универсальная платформа Windows приложении, см. в разделе [функции CRT, которые не поддерживаются в приложениях универсальная платформа Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) и [Win32 и com для приложений UWP](/uwp/win32-and-com/win32-and-com-for-uwp-apps).

1. Включите (`#include`) все необходимые среда выполнения Windows, среда выполнения Windows C++ библиотека шаблонов или C++ заголовки стандартной библиотеки.

   [!code-cpp[wrl-consume-event#2](../codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]

   `Windows.Devices.Enumeration.h` объявляет типы, необходимые для перечисления устройств.

   Рекомендуется использовать директиву `using namespace` в CPP-файле, чтобы сделать код более удобочитаемым.

2. Объявите локальные переменные для приложения. Этот пример проводит подсчет количества перечисленных устройств и токенов регистрации, которые позволяют в дальнейшем отменять подписку на события.

   [!code-cpp[wrl-consume-event#7](../codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]

3. Инициализируйте среда выполнения Windows.

   [!code-cpp[wrl-consume-event#3](../codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]

4. Создайте объект [события](event-class-wrl.md) , который синхронизирует завершение процесса перечисления с основным приложением.

   [!code-cpp[wrl-consume-event#4](../codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]

   > [!NOTE]
   > Это событие выполняется только для демонстрации в составе консольного приложения. В этом примере используется объект-событие, чтобы удостовериться, что асинхронная операция окончится до завершения приложения. В большинстве приложений обычно не ожидается выполнение асинхронной операции.

5. Создайте фабрику активации для интерфейса `IDeviceWatcher`.

   [!code-cpp[wrl-consume-event#5](../codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]

   Среда выполнения Windows использует полные имена для указания типов. Параметр `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` — это строка, предоставляемая среда выполнения Windows и содержащая имя требуемого класса среды выполнения.

6. Создание объекта `IDeviceWatcher`.

   [!code-cpp[wrl-consume-event#6](../codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]

7. Используйте функцию `Callback` для подписки на события `Added`, `EnumerationCompleted` и `Stopped`.

   [!code-cpp[wrl-consume-event#8](../codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]

   Обработчик событий `Added` увеличивает число перечисленных устройств. Он останавливает процесс перечисления после обнаружения десяти устройств.

   Обработчик событий `Stopped` удаляет обработчики событий и задает событие завершения.

   Обработчик событий `EnumerationCompleted` останавливает процесс перечисления. Рекомендуется обрабатывать это событие, если имеется менее десяти устройств.

   > [!TIP]
   > В этом примере используется лямбда-выражение для определения обратных вызовов. Можно также использовать объекты функций (операторов), указатели функций или объекты [std:: Function](../../standard-library/function-class.md) . Дополнительные сведения о лямбда-выражениях см. в разделе [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md).

8. Запустите процесс перечисления.

   [!code-cpp[wrl-consume-event#9](../codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]

9. Дождитесь завершения процесса перечисления, а затем выведите сообщение. Все объекты `ComPtr` и RAII покидают область действия и автоматически освобождаются.

   [!code-cpp[wrl-consume-event#10](../codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]

Ниже приведен полный пример.

[!code-cpp[wrl-consume-event#1](../codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и вставьте в проект Visual Studio или вставьте в файл с именем `wrl-consume-events.cpp` а затем выполните следующую команду в окне **командной строки Visual Studio** .

`cl.exe wrl-consume-events.cpp runtimeobject.lib`

## <a name="see-also"></a>См. также раздел

[Библиотека шаблонов C++ среды выполнения Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)
