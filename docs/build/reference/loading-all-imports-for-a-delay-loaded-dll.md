---
title: "Загрузка всех импортов для библиотеки DLL с отложенной загрузкой | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__HrLoadAllImportsForDll - параметр компоновщика"
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Загрузка всех импортов для библиотеки DLL с отложенной загрузкой
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Функция **\_\_HrLoadAllImportsForDll**, определенная в файле delayhlp.cpp, дает компоновщику указание загрузить все импорты из библиотеки DLL, указанной в параметре компоновщика [\/delayload](../../build/reference/delayload-delay-load-import.md).  
  
 Загрузка всех импортов позволяет свести обработку ошибок в коде воедино и не использовать обработку исключений вокруг фактических вызовов импортов.  Это также позволяет избежать ситуации, в которой происходит частичный сбой приложения в процессе вследствие того, что вспомогательной функции не удается выполнить загрузку импорта.  
  
 Вызов функции **\_\_HrLoadAllImportsForDll** не изменяет поведение функций\-обработчиков и обработки ошибок; дополнительные сведения см. в разделе [Обработка ошибок и уведомления](../../build/reference/error-handling-and-notification.md).  
  
 Имя библиотеки DLL переданное **\_\_HrLoadAllImportsForDll** сравнивается с именем, хранящиеся внутри самой библиотеке DLL и чувствительно к регистру.  
  
 В следующем примере показан способ вызова **\_\_HrLoadAllImportsForDll**:  
  
```  
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {  
   printf ( "failed on snap load, exiting\n" );  
   exit(2);  
}  
```  
  
## См. также  
 [Поддержка компоновщика для DLLs, загружаемых с задержкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)