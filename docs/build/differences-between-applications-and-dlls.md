---
title: "Различия между приложениями и библиотеками DLL | Microsoft Docs"
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
  - "приложения [C++], или DLL-библиотеки"
  - "DLL-библиотеки [C++], или приложения"
  - "исполняемые файлы [C++], библиотеки DLL или приложения"
ms.assetid: 8f271523-d8d0-4ad1-84d2-0c5645d7fd5b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Различия между приложениями и библиотеками DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Несмотря на то, что библиотеки DLL и приложения являются исполняемыми программными модулями, между ними существует ряд различий.  Для конечного пользователя наиболее очевидным отличием является то, что библиотеки DLL не являются программами и не могут выполняться напрямую.  С точки зрения системы существует два фундаментальных различия между приложениями и библиотеками DLL:  
  
-   В системе может выполняться несколько экземпляров приложения одновременно, в то время как библиотека DLL может выполняться только в одном экземпляре.  
  
-   В приложении может быть стек, глобальная память, дескрипторы файлов и очередь сообщений — всего этого не может быть в библиотеке DLL.  
  
## Выберите действие.  
  
-   [Экспорт из DLL](../build/exporting-from-a-dll.md)  
  
-   [Привязка исполняемого файла к библиотеке DLL](../build/linking-an-executable-to-a-dll.md)  
  
-   [Инициализацию DLL](../build/initializing-a-dll.md)  
  
## Дополнительные сведения  
  
-   [Преимущества использования библиотек DLL](../build/advantages-of-using-dlls.md)  
  
-   [Общие сведения о библиотеках DLL, не являющихся MFC](../Topic/Non-MFC%20DLLs:%20Overview.md)  
  
-   [Обычные библиотеки DLL, статически компонуемые с MFC](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Обычные библиотеки DLL, динамически компонуемые с MFC](../Topic/Regular%20DLLs%20Dynamically%20Linked%20to%20MFC.md)  
  
-   [Общие сведения о библиотеках \(DLL\) расширения](../build/extension-dlls-overview.md)  
  
## См. также  
 [DLL в Visual C\+\+](../build/dlls-in-visual-cpp.md)