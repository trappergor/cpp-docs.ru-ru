---
title: "Поддержка компоновщика для DLLs, загружаемых с задержкой | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "отложенная загрузка библиотек DLL, поддержка компоновщика"
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Поддержка компоновщика для DLLs, загружаемых с задержкой
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Компоновщик Visual C\+\+ сейчас поддерживает загрузку DLLs с задержкой.  Это снимает необходимость использовать функции [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] **LoadLibrary** и **GetProcAddress** для реализации загрузки DLL с задержкой.  
  
 В предыдущих версиях Visual C\+\+ 6.0 был только один способ загрузить DLL во время выполнения: использовать **LoadLibrary** и **GetProcAddress**; операционная система могла бы загрузить DLL при выполнении или использовать загруженные модули DLL.  
  
 Начиная с Visual C\+\+ 6.0, при статической компоновке с DLL компоновщик предоставляет параметры для задержки загрузки DLL до тех пор, пока программа не вызовет функцию, в которой содержится DLL.  
  
 Приложение может задержать загрузку DLL при помощи параметра компоновщика [\/DELAYLOAD \(Delay Load Import\)](../../build/reference/delayload-delay-load-import.md) со вспомогательной функцией \(реализацией по умолчанию предоставляемой Visual C\+\+\).  Вспомогательная функция будет загружать DLL во время выполнения, вызывая **LoadLibrary** и **GetProcAddress**.  
  
 Следует установить задержку в загрузке DLL, если:  
  
-   Ваша программа может не вызвать функцию в DLL.  
  
-   Функция в DLL может не получить вызов до тех пор, пока не будет выполняться в программе.  
  
 Задержка в загрузке DLL может быть указана при построении .EXE или .DLL проекта.  Проекту .DLL, который задерживает загрузку одного или более DLLs, не следует самому вызывать загружаемую с задержкой точки входа в Dllmain.  
  
 В следующих подразделах приведено описание DLLs, загружаемых с задержкой:  
  
-   [Указание DLLs для загрузки с задержкой.](../../build/reference/specifying-dlls-to-delay-load.md)  
  
-   [Явная выгрузка библиотеки DLL, загруженной с задержкой.](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
-   [Загрузка всех Imports для DLL, загружаемых с задержкой.](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)  
  
-   [Связывание Imports.](../../build/reference/binding-imports.md)  
  
-   [Обработка ошибок и предупреждений.](../../build/reference/error-handling-and-notification.md)  
  
-   [Сохранение отложенно загружаемых импортированных файлов.](../../build/reference/dumping-delay-loaded-imports.md)  
  
-   [Ограничения библиотек DLL, загружаемых с задержкой.](../../build/reference/constraints-of-delay-loading-dlls.md)  
  
-   [Понятие вспомогательной функции.](http://msdn.microsoft.com/ru-ru/6279c12c-d908-4967-b0b3-cabfc3e91d3d)  
  
-   [Разработка вашей собственной вспомогательной функции.](../../build/reference/developing-your-own-helper-function.md)  
  
## См. также  
 [DLL в Visual C\+\+](../../build/dlls-in-visual-cpp.md)   
 [Компоновка](../Topic/Linking.md)