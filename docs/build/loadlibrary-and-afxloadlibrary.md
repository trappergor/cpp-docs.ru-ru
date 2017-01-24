---
title: "Функции LoadLibrary и AfxLoadLibrary | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LoadLibrary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxLoadLibrary - метод"
  - "DLL-библиотеки [C++], AfxLoadLibrary"
  - "DLL-библиотеки [C++], LoadLibrary"
  - "явное связывание [C++]"
  - "LoadLibrary - метод"
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Функции LoadLibrary и AfxLoadLibrary
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Процессы вызывают функцию [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187) \(или [AfxLoadLibrary](../Topic/AfxLoadLibrary.md)\) для явного связывания с библиотекой DLL.  При успешном завершении функция сопоставляет указанную библиотеку DLL с адресным пространством вызывающего процесса и возвращает дескриптор библиотеки DLL, который можно использовать с другими функциями для явного связывания — например, `GetProcAddress` и `FreeLibrary`.  
  
 Функция `LoadLibrary` пытается обнаружить библиотеку DLL с помощью того же метода поиска, который используется для неявного связывания.  Если система не может найти библиотеку DLL или функция точки входа возвращает значение FALSE, функция `LoadLibrary` возвращает значение NULL.  Если в вызове функции `LoadLibrary` указан модуль DLL, уже сопоставленный с адресным пространством вызывающего процесса, функция возвращает дескриптор библиотеки DLL и увеличивает счетчик ссылок модуля.  
  
 Если у библиотеки DLL есть функция точки входа, операционная система вызывает эту функцию в контексте потока, в котором вызвана функция `LoadLibrary`.  Функция точки входа не вызывается, если библиотека DLL уже присоединена к процессу в результате предыдущего вызова функции `LoadLibrary`, за которым не последовал вызов функции `FreeLibrary`.  
  
 Для приложений MFC, загружающих библиотеки расширений DLL, рекомендуется использовать функцию `AfxLoadLibrary` вместо функции `LoadLibrary`.  Функция `AfxLoadLibrary` обрабатывает синхронизацию потока до вызова функции `LoadLibrary`.  Интерфейс \(прототип\) функции `AfxLoadLibrary` такой же, как у функции `LoadLibrary`.  
  
 Если системе Windows не удается загрузить библиотеку DLL, процесс может попытаться исправить последствия ошибки.  Например, процесс может уведомить пользователя об ошибке и запросить у него другой путь к библиотеке DLL.  
  
> [!IMPORTANT]
>  Если код будет запускаться под управлением Windows NT 4, Windows 2000 или Windows XP \(до пакета обновления SP1\), необходимо указывать полный путь для всех библиотек DLL.  В этих операционных системах при загрузке файлов в первую очередь поиск идет в текущем каталоге.  Если не указать полный путь к файлу, может быть загружен не тот файл, который требуется.  
  
## Выберите действие.  
  
-   [Неявное связывание](../Topic/Linking%20Implicitly.md)  
  
-   [Определение подходящего метода связывания](../build/determining-which-linking-method-to-use.md)  
  
## Дополнительные сведения  
  
-   [Путь поиска, используемый Windows для поиска библиотеки DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
-   [Функции FreeLibrary и AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## См. также  
 [DLL в Visual C\+\+](../build/dlls-in-visual-cpp.md)   
 [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187)   
 [AfxLoadLibrary](../Topic/AfxLoadLibrary.md)