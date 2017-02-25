---
title: "Практическое руководство. Обработка событий с использованием WRL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Практическое руководство. Обработка событий с использованием WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот документ показывает, как использовать [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) для подписки на события объекта [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] и обработки этих событий.  
  
 Для более базового примера, который создает экземпляр этого компонента и получает значение свойства, см. [Практическое руководство. Активация и использование компонента среды выполнения Windows](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
## Подписка на события и их обработка  
 Следующие действия запускают объект `ABI::Windows::System::Threading::IDeviceWatcher` и используют обработчики событий для отслеживания прогресса.  Интерфейс `IDeviceWatcher` позволяет перечислять устройства асинхронно или в фоновом режиме и получать уведомление при добавлении, удалении или изменении устройства.  Функция [Обратный вызов](../windows/callback-function-windows-runtime-cpp-template-library.md) является важной частью этого примера, поскольку она позволяет ему определить обработчики событий, которые обрабатывают результаты фоновых операций.  Полный пример кода выглядит следующим образом.  
  
> [!WARNING]
>  Хотя обычно используется [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] в приложении [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], в этом образце для иллюстрации используется консольное приложение.  Функции, такие как `wprintf_s`, недоступны из приложения [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о типах и функциях, которые можно использовать в приложении [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] см. [Функции CRT, не поддерживаемые \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) и [Win32 и модели COM для приложений Магазина Windows](http://msdn.microsoft.com/library/windows/apps/br205757.aspx).  
  
1.  Включите \(`#include`\) все необходимые заголовки [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] или стандартной библиотеки C\+\+.  
  
     [!CODE [wrl-consume-event#2](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#2)]  
  
     Windows.Devices.Enumeration.h объявляет типы, необходимые для перечисления устройств.  
  
     Рекомендуется использовать директиву `using namespace` в CPP\-файле, чтобы сделать код более удобочитаемым.  
  
2.  Объявите локальные переменные для приложения.  Этот пример проводит подсчет количества перечисленных устройств и токенов регистрации, которые позволяют позже отменять подписку на события.  
  
     [!CODE [wrl-consume-event#7](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#7)]  
  
3.  Инициализируйте [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
     [!CODE [wrl-consume-event#3](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#3)]  
  
4.  Создайте объект [Событие](../windows/event-class-windows-runtime-cpp-template-library.md), который синхронизирует завершение процесса перечисления c основным приложением.  
  
     [!CODE [wrl-consume-event#4](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#4)]  
  
    > [!NOTE]
    >  Это событие только для демонстрации в составе консольного приложения.  В этом примере используется событие, чтобы гарантировать, что асинхронная операция окончится до завершения приложения.  В большинстве приложений обычно не ожидается выполнение асинхронной операции.  
  
5.  Создание фабрики активации для интерфейса `IDeviceWatcher`.  
  
     [!CODE [wrl-consume-event#5](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#5)]  
  
     В [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] используются полные имена для идентификации типов.  Параметр `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` является строкой, предоставляемой [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], которая содержит требуемое имя класса среды выполнения.  
  
6.  Создайте объект `IDeviceWatcher`.  
  
     [!CODE [wrl-consume-event#6](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#6)]  
  
7.  Используйте функцию `Callback` для подписки на события `Added`, `EnumerationCompleted` и `Stopped`.  
  
     [!CODE [wrl-consume-event#8](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#8)]  
  
     Обработчик событий `Added` увеличивает число перечисленных устройств.  Он останавливает процесс перечисления после обнаружения десяти устройств.  
  
     Обработчик событий `Stopped` удаляет обработчики событий и задает событие завершения.  
  
     Обработчик событий `EnumerationCompleted` останавливает процесс перечисления.  Рекомендуется обрабатывать это событие в случае, если устройств меньше десяти.  
  
    > [!TIP]
    >  В этом примере используется лямбда\-выражение для определения обратных вызовов.  Можно также использовать объекты функций \(функторы\), указатели на функции или объекты [std::function](../standard-library/function-class.md).  Дополнительные сведения о лямбда\-выражениях см. в разделе [Лямбда\-выражения](../cpp/lambda-expressions-in-cpp.md).  
  
8.  Запуск процесса перечисления.  
  
     [!CODE [wrl-consume-event#9](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#9)]  
  
9. Дождитесь завершения процесса перечисления, а затем выведите сообщение.  Все объекты `ComPtr` и RAII покидают область действия и автоматически освобождаются.  
  
     [!CODE [wrl-consume-event#10](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#10)]  
  
 Ниже приведен полный пример.  
  
 [!CODE [wrl-consume-event#1](../CodeSnippet/VS_Snippets_Misc/wrl-consume-event#1)]  
  
## Компиляция кода  
 Чтобы скомпилировать код, скопируйте и вставьте его в проект Visual Studio или в файл с именем `wrl-consume-events.cpp`, а затем выполните в окне командной строки Visual Studio следующую команду.  
  
 **cl.exe wrl\-consume\-events.cpp runtimeobject.lib**  
  
## См. также  
 [Библиотека шаблонов C\+\+ среды выполнения Windows \(WRL\)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)