---
title: "Как: использование winmdidl.exe и midlrt.exe для создания h-файлы из метаданных windows | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 4be8ba11-c223-44ad-9256-7e1edae9a7bc
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f09bdc306bc91184b546ff951dc36b94cda72bb5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-winmdidlexe-and-midlrtexe-to-create-h-files-from-windows-metadata"></a>Практическое руководство. Использование winmdidl.exe и midlrt.exe для создания H-файлов из метаданных Windows
Winmdidl.exe и midlrt.exe разрешают взаимодействие COM-уровня между машинным кодом C++ и компонентами среды выполнения Windows. Winmdidl.exe принимает в качестве входных данных WINMD-файл, содержащий метаданные для компонента среды выполнения Windows, и выводит IDL-файл. Midlrt.exe преобразовывает этот IDL-файл в файлы заголовков, которые можно использовать в коде C++. Оба инструмента запускаются с помощью командной строки.  
  
 Эти инструменты используются в следующих двух сценариях:  
  
-   создание пользовательских IDL-файлов и файлов заголовков, чтобы приложение C++, написанное с помощью библиотеки шаблонов среды выполнения Windows (WRL), могло использовать пользовательский компонент среды выполнения Windows;  
  
-   создание прокси-сервера и файлов-заглушек для определяемых пользователем типов событий в компоненте среды выполнения Windows. Дополнительные сведения см. в разделе [пользовательские события и методы доступа к событиям в компонентах среды выполнения Windows](/uwp/winrt-components/custom-events-and-event-accessors-in-windows-runtime-components).  
  
 Эти инструменты требуются только для синтаксического анализа пользовательских WINMD-файлов. IDL- и H-файлы для компонентов операционной системы Windows уже созданы. По умолчанию в [!INCLUDE[win81](../misc/includes/win81_md.md)], они находятся в \Program файлы (x86) \Windows Kits\8.1\Include\winrt\\.  
  
## <a name="location-of-the-tools"></a>Расположение инструментов  
 По умолчанию в [!INCLUDE[win81](../misc/includes/win81_md.md)], winmdidl.exe и midlrt.exe расположены в C:\Program Files (x86) \Windows Kits\8.1\\. Различные версии этих инструментов также доступны в папках \bin\x86\ и \bin\x64\.  
  
## <a name="winmdidl-command-line-arguments"></a>Аргументы командной строки winmdidl  
  
```  
Winmdidl.exe [/nologo] [/supressversioncheck] [/time] [/outdir:dir] [/banner:file] [/utf8] Winmdfile  
```  
  
 `/nologo`  
 Блокирует отображение в консоли сообщения об авторских правах и номере версии winmdidl.  
  
 `/supressversioncheck`  
 Не используется.  
  
 `/time`  
 Выводит общее время выполнения в окно консоли.  
  
 / outdir:\<dir >  
 Задает выходной каталог. Если путь содержит пробелы, используйте кавычки. Выходной каталог по умолчанию —  *\<диска >*: \Users\\*\<имя пользователя >*\AppData\Local\VirtualStore\Program Files (x86) \Microsoft Visual Studio 12.0\\.  
  
 `/banner:<file>`  
 Указывает файл, содержащий пользовательский текст, который необходимо вставить в начало сообщения по умолчанию об авторских правах и версии winmdidl в верхней части сгенерированного IDL-файла. Если путь содержит пробелы, используйте кавычки.  
  
 `/utf8`  
 Файл будет отформатирован в кодировке UTF-8.  
  
 `Winmdfile`  
 Имя WINMD-файла для анализа. Если путь содержит пробелы, используйте кавычки.  
  
## <a name="midlrt-command-line-arguments"></a>Аргументы командной строки midlrt  
 В разделе [MIDLRT и среды выполнения Windows компонентов](http://msdn.microsoft.com/library/windows/desktop/hh869900\(v=vs.85\).aspx).  
  
## <a name="examples"></a>Примеры  
 В следующем примере показана работа команды winmdidl в командной строке Visual Studio x86. Она определяет выходную папку и файл, содержащий специальный текст баннера, который следует добавить в сгенерированный IDL-файл.  
  
 **C:\Program Files (x86) \Microsoft Visual Studio 12.0 >/nologo winmdidl /outdir:c:\users\giraffe\documents\ /banner:c:\users\giraffe\documents\banner.txt 2013\Projects\Test_for_winmdidl\Debug\ C:\Users\giraffe\Documents\Visual Studio» Test_for_winmdidl\test_for_winmdidl.winmd»**  
  
 В следующем примере показан вывод в окно консоли результата работы команды winmdidl, который указывает, что операция выполнена успешно.  
  
 **Создание c:\users\giraffe\documents\\\Test_for_winmdidl.idl**  
  
 Затем для созданного IDL-файла выполняется команда midlrt. Обратите внимание, что **metadata_dir** аргумента указывается после имени IDL-файла. Путь \WinMetadata\ является обязательным — это расположение для windows.winmd.  
  
 **C:\Program Files (x86) \Microsoft Visual Studio 12.0 > /metadata_dir «c:\users\mblome\documents\test_for_winmdidl.idl» midlrt «C:\Windows\System32\WinMetadata»**  
  
## <a name="remarks"></a>Примечания  
 Выходной файл операции winmdidl будет иметь то же имя, что и входной файл, но с расширением IDL.  
  
 При разработке компонента среды выполнения Windows, который будет доступен из WRL, можно указать в качестве действий после сборки запуск инструментов winmdidl.exe и midlrt.exe для создания IDL- и H-файлов при каждой сборке. Пример см. в разделе [создание событий в компонентах среды выполнения Windows](/uwp/winrt-components/raising-events-in-windows-runtime-components).