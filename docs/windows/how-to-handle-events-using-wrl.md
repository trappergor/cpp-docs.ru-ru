---
title: 'Как: обработка событий с помощью WRL | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a3c1666d1c79414beddc5b5e3ccc03953c92e902
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-handle-events-using-wrl"></a>Практическое руководство. Обработка событий с использованием WRL
В этом документе показано, как использовать среды выполнения C++ шаблон библиотеки Windows (WRL) для подписки и обрабатывать события объекта среды выполнения Windows.  
  
 Более простой пример, который создает экземпляр этого компонента и извлекает значение свойства, в разделе [как: активация и использование компонента среды выполнения Windows](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
## <a name="subscribing-to-and-handling-events"></a>Подписка на события и их обработка  
 Следующие действия запускают объект `ABI::Windows::System::Threading::IDeviceWatcher` и используют обработчики событий для отслеживания прогресса. Интерфейс `IDeviceWatcher` позволяет перечислять устройства асинхронно (или в фоновом режиме) и получать уведомление при добавлении, удалении и изменении устройства. [Обратного вызова](../windows/callback-function-windows-runtime-cpp-template-library.md) функция является важной частью в этом примере, поскольку она позволяет определить обработчики событий, которые обрабатывают результаты фоновых операций. Далее приведен полный пример.  
  
> [!WARNING]
>  Несмотря на то, что обычно используется библиотека шаблонов C++ среды выполнения Windows в приложении универсальной платформы Windows, в этом примере используется консольное приложение для иллюстрации. Функции, такие как `wprintf_s` недоступны в приложении универсальной платформы Windows. Дополнительные сведения о типах и функции, которые можно использовать в приложении универсальной платформы Windows см. в разделе [функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) и [Win32 и COM для приложений UWP](/uwp/win32-and-com/win32-and-com-for-uwp-apps).  
  
1.  Включить (`#include`) все необходимые среды выполнения Windows, библиотека шаблонов C++ среды выполнения Windows или заголовков стандартной библиотеки C++.  
  
     [!code-cpp[wrl-consume-event#2](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]  
  
     В файле Windows.Devices.Enumeration.h объявлены типы, необходимые для перечисления устройств.  
  
     Рекомендуется использовать директиву `using namespace` в CPP-файле, чтобы сделать код более удобочитаемым.  
  
2.  Объявите локальные переменные для приложения. Этот пример проводит подсчет количества перечисленных устройств и токенов регистрации, которые позволяют в дальнейшем отменять подписку на события.  
  
     [!code-cpp[wrl-consume-event#7](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]  
  
3.  Инициализирует среду выполнения Windows.  
  
     [!code-cpp[wrl-consume-event#3](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]  
  
4.  Создание [событие](../windows/event-class-windows-runtime-cpp-template-library.md) объект, который синхронизирует завершение процесса перечисления с основным приложением.  
  
     [!code-cpp[wrl-consume-event#4](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  Это событие выполняется только для демонстрации в составе консольного приложения. В этом примере используется объект-событие, чтобы удостовериться, что асинхронная операция окончится до завершения приложения. В большинстве приложений обычно не ожидается выполнение асинхронной операции.  
  
5.  Создайте фабрику активации для интерфейса `IDeviceWatcher`.  
  
     [!code-cpp[wrl-consume-event#5](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]  
  
     Среда выполнения Windows использует полные имена для определения типов. `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` Параметр представляет собой строку, предоставляемые средой выполнения Windows и содержит имя класса необходимая среда выполнения.  
  
6.  Создайте объект `IDeviceWatcher`.  
  
     [!code-cpp[wrl-consume-event#6](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]  
  
7.  Используйте функцию `Callback` для подписки на события `Added`, `EnumerationCompleted` и `Stopped`.  
  
     [!code-cpp[wrl-consume-event#8](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]  
  
     Обработчик событий `Added` увеличивает число перечисленных устройств. Он останавливает процесс перечисления после обнаружения десяти устройств.  
  
     Обработчик событий `Stopped` удаляет обработчики событий и задает событие завершения.  
  
     Обработчик событий `EnumerationCompleted` останавливает процесс перечисления. Рекомендуется обрабатывать это событие, если имеется менее десяти устройств.  
  
    > [!TIP]
    >  В этом примере используется лямбда-выражение для определения обратных вызовов. Можно также использовать объекты функций (функторы), указатели на функции или [std::function](../standard-library/function-class.md) объектов. Дополнительные сведения о лямбда-выражениях см. в разделе [Лямбда-выражения](../cpp/lambda-expressions-in-cpp.md).  
  
8.  Запустите процесс перечисления.  
  
     [!code-cpp[wrl-consume-event#9](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]  
  
9. Дождитесь завершения процесса перечисления, а затем выведите сообщение. Все объекты `ComPtr` и RAII покидают область действия и автоматически освобождаются.  
  
     [!code-cpp[wrl-consume-event#10](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]  
  
 Ниже приведен полный пример.  
  
 [!code-cpp[wrl-consume-event#1](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или в файл с именем `wrl-consume-events.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe wrl-consume-events.cpp runtimeobject.lib**  
  
## <a name="see-also"></a>См. также  
 [Библиотека шаблонов C++ среды выполнения Windows (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)