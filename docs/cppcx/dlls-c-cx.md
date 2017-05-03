---
title: "Библиотеки DLL (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5b8bcc57-64dd-4c54-9f24-26a25bd5dddd
caps.latest.revision: 21
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 21
---
# Библиотеки DLL (C++/CX)
С помощью Visual Studio можно создать стандартную библиотеку DLL Win32 или библиотеку DLL компонента [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], которую смогут использовать приложения [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]. Стандартная библиотека DLL, созданная с помощью версии Visual Studio или версии компилятора Visual C\+\+ более ранней, чем [!INCLUDE[vs_dev11_long](../cppcx/includes/vs-dev11-long-md.md)], может не загрузиться в приложении [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] надлежащим образом и не пройти проверку приложения в [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)].  
  
## DLL компонентов [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]  
 В большинстве случаев при необходимости создания библиотеки DLL для использования в приложении [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] создавайте такую библиотеку как компонент [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] с помощью шаблона проекта с тем же именем. Можно создать проект компонента [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] для библиотек DLL, содержащих открытые или закрытые типы [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. К компоненту [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] могут обращаться приложения, написанные на любом языке, совместимом с [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. По умолчанию в параметрах компилятора для проекта компонента [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] задан ключ **\/ZW**. WINMD\-файл должен иметь одно имя с корневым пространством имен. Например, экземпляр класса с именем A.B.C.MyClass может быть создан, только если он определен в файле метаданных с именем A.winmd, A.B.winmd или A.B.C.winmd. Имя DLL\-файла не обязательно должно соответствовать имени WINMD\-файла.  
  
 Для получения дополнительной информации см. [Создание компонентов среды выполнения Windows в C\+\+](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md).  
  
#### Указание ссылки на двоичный файл компонента [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] сторонних разработчиков  
  
1.  Откройте контекстное меню для проекта, в котором будет использоваться библиотека DLL, и выберите пункт **Свойства**. На странице **Общие свойства** нажмите кнопку **Добавить новую ссылку**.  
  
2.  Компонент [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] состоит из DLL\-файла и WINMD\-файла, содержащего метаданные. Обычно эти файлы расположены в одной и той же папке. В левой области диалогового окна **Добавление ссылки** нажмите кнопку **Обзор** и перейдите к расположению DLL\-файла и его WINMD\-файла. Дополнительные сведения см. в разделе [Учебник. Создание и использование пакетов SDK для расширений](http://msdn.microsoft.com/ru-ru/001e2fca-3d56-43ab-a5e0-0561d085679f).  
  
## Стандартные библиотеки DLL  
 Можно создать стандартную библиотеку DLL для кода C\+\+, в котором не используются и не создаются открытые типы [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], а используются существующие типы из приложения [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]. Используйте тип проекта DLL [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)], если необходимо перенести существующую библиотеку DLL для компиляции в этой версии Visual Studio без конвертирования кода в проект среды выполнения Windows. При выполнении следующих действий библиотека DLL будет развернута вместе с исполняемым файлом приложения в APPX\-пакете.  
  
#### Создание стандартной библиотеки DLL в Visual Studio  
  
1.  В строке меню выберите **Файл**, **Создать**, **Проект**, а затем выберите шаблон DLL [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)].  
  
2.  Введите имя проекта и нажмите кнопку **ОК**.  
  
3.  Добавьте код. Не забудьте добавить выражение `__declspec(dllexport)` для функций, которые планируется экспортировать, например `__declspec(dllexport) Add(int I, in j);`  
  
4.  Добавьте выражение `#include winapifamily.h`, чтобы включить этот файл заголовка из Windows SDK для приложений [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)], и задайте макрос `WINAPI_FAMILY=WINAPI_PARTITION_APP`.  
  
#### Указание ссылки на проект стандартной библиотеки DLL из того же решения  
  
1.  Откройте контекстное меню для проекта, в котором будет использоваться библиотека DLL, и выберите пункт **Свойства**. На странице **Общие свойства** нажмите кнопку **Добавить новую ссылку**.  
  
2.  В левой области выберите **Решение** и установите соответствующий флажок в правой области.  
  
3.  В файлах исходного кода добавьте оператор `#include` для файла заголовков библиотеки DLL.  
  
#### Указание ссылки на двоичный файл стандартной библиотеки DLL  
  
1.  Скопируйте DLL\-файл, LIB\-файл и файл заголовков в нужное расположение, например в папку текущего проекта.  
  
2.  Откройте контекстное меню для проекта, в котором будет использоваться библиотека DLL, и выберите пункт **Свойства**. На странице **Свойства конфигурации** \> **Компоновщик** \> **Ввод** добавьте LIB\-файл в качестве зависимости.  
  
3.  В файлах исходного кода добавьте оператор `#include` для файла заголовков библиотеки DLL.  
  
#### Миграция существующей библиотеки DLL Win32 для обеспечения совместимости с приложениями [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]  
  
1.  Создайте проект типа DLL [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] и добавьте в него существующий код.  
  
2.  Добавьте выражение `#include winapifamily.h`, чтобы включить этот файл заголовка из Windows SDK для приложений [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)], и задайте макрос `WINAPI_FAMILY=WINAPI_PARTITION_APP`.  
  
3.  В файлах исходного кода добавьте оператор `#include` для файла заголовков библиотеки DLL.  
  
## См. также  
 [\(NOTINBUILD\) Дополнительные разделы](http://msdn.microsoft.com/ru-ru/1ccff0cf-a6cc-47ef-a05f-eba6307b3ced)