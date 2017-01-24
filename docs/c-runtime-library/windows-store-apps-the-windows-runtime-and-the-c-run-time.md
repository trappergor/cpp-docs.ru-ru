---
title: "Приложения для Магазина Windows, среда выполнения Windows и среда выполнения C | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Приложения для Магазина Windows, среда выполнения Windows и среда выполнения C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Приложения [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] представляют собой программы, запускающиеся в среде [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], которая выполняется в [!INCLUDE[win8](../build/includes/win8_md.md)].  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] — это надежная среда, контролирующая функции, переменные и ресурсы, доступные приложению [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)].  Однако ограничения, предусмотренные в среде [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], не позволяют использовать большинство функций библиотеки времени выполнения C \(CRT\) в приложениях [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)].  
  
 Среда [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] не поддерживает следующие возможности CRT:  
  
-   Большая часть функций CRT, связанных с неподдерживаемой функциональностью.  
  
     Например, приложение [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] не может создать процесс с помощью семейств подпрограмм `exec` и `spawn`.  
  
     Если функция CRT не поддерживается в приложении [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], это указывается в статье по данной функции.  
  
-   Большая часть функций, работающих с многобайтовыми символами и строками.  
  
     Однако тексты Юникод и ANSI поддерживаются.  
  
-   Консольные приложения и аргументы командной строки.  
  
     Однако классические приложения по\-прежнему поддерживают консоль и аргументы командной строки.  
  
-   Переменные среды.  
  
-   Понятие текущего рабочего каталога.  
  
-   Приложения и DLL [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], которые статически скомпонованы с CRT и собираются с использованием параметров компилятора [\/MT](../build/reference/md-mt-ld-use-run-time-library.md) или `/MTd`.  
  
     Это означает, что приложение использует многопоточную статическую версию CRT.  
  
-   Приложения, которые создаются с использованием параметра компилятора [\/MDd](../build/reference/md-mt-ld-use-run-time-library.md).  
  
     То есть, отладочная, многопоточная и DLL\-специфичная версия CRT.  Такое приложение не поддерживается в [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)].  
  
 Полный список функций CRT, которые недоступны в приложениях [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], и варианты альтернативных функций см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## См. также  
 [Совместимость](../c-runtime-library/compatibility.md)   
 [Функции CRT, которые не поддерживаются средой выполнения Windows](../Topic/Windows%20Runtime%20Unsupported%20CRT%20Functions.md)   
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)