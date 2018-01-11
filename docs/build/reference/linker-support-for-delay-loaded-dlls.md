---
title: "Поддержка компоновщика для DLLs, загружаемых с задержкой | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 83e75df963889730e4514c38d0551af241a788fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-support-for-delay-loaded-dlls"></a>Поддержка компоновщика для DLLs, загружаемых с задержкой
Компоновщик Visual C++ теперь поддерживает отложенной загрузкой библиотек DLL. Это снимает необходимость использования функций Windows SDK **LoadLibrary** и **GetProcAddress** для реализации отложенная загрузка библиотеки DLL.  
  
 До Visual C++ 6.0: единственный способ загрузки библиотеки DLL во время выполнения с помощью **LoadLibrary** и **GetProcAddress**; операционная система загружает библиотеку DLL при исполняемый файл или библиотеку DLL с помощью его загрузки.  
  
 Начиная с Visual C++ 6.0, если статическая компоновка с библиотекой DLL, компоновщик предоставляет параметры для задержки загрузки библиотеки DLL, пока программа вызывает функцию в этой библиотеке DLL.  
  
 Приложение может задержать загрузку DLL при помощи [/DELAYLOAD (Delay Load Import)](../../build/reference/delayload-delay-load-import.md) компоновщика со вспомогательной функцией (реализацией по умолчанию предоставляемой Visual C++). Вспомогательную функцию загрузки библиотеки DLL во время выполнения путем вызова **LoadLibrary** и **GetProcAddress** для вас.  
  
 Отложенная загрузка библиотеки DLL, если необходимо учитывать.  
  
-   Программа не может вызвать функцию в DLL.  
  
-   Функции в DLL не может вызываться только на поздних этапах выполнения программы.  
  
 Отложенная загрузка библиотеки DLL может указываться при построении. Exe-ФАЙЛ или. Проект библиотеки DLL. ОБЪЕКТ. Проект библиотеки DLL, который задерживает загрузку одного или нескольких библиотек DLL следует не самому вызывать точку входа, загружаемых с задержкой в Dllmain.  
  
 В следующих разделах описываются отложенная загрузка библиотек DLL:  
  
-   [Задание библиотек DLL с отложенной загрузкой](../../build/reference/specifying-dlls-to-delay-load.md)  
  
-   [Явная выгрузка библиотеки DLL с отложенной загрузкой](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
-   [Загрузка всех импортов для библиотеки DLL с отложенной загрузкой](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)  
  
-   [Привязка Imports](../../build/reference/binding-imports.md)  
  
-   [Обработка ошибок и предупреждений](../../build/reference/error-handling-and-notification.md)  
  
-   [Сохранение отложенно загружаемых импортированных элементов](../../build/reference/dumping-delay-loaded-imports.md)  
  
-   [Ограничения библиотек DLL с отложенной загрузкой](../../build/reference/constraints-of-delay-loading-dlls.md)  
  
-   [Понятие вспомогательной функции](understanding-the-helper-function.md)  
  
-   [Разработка собственной вспомогательной функции](../../build/reference/developing-your-own-helper-function.md)  
  
## <a name="see-also"></a>См. также  
 [Библиотеки DLL в Visual C++](../../build/dlls-in-visual-cpp.md)   
 [Компоновка](../../build/reference/linking.md)