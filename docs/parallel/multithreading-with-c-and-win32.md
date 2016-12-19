---
title: "Реализация многопоточности на языке C с помощью функций Win32 | Microsoft Docs"
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
  - "многопоточность [C++], C и Win32"
  - "работа с потоками [C]"
  - "работа с потоками [C++], C и Win32"
  - "Visual C, многопоточность"
  - "Win32 [C++], многопоточность"
  - "приложения Win32 [C++], многопоточность"
  - "Windows API [C++], многопоточность"
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Реализация многопоточности на языке C с помощью функций Win32
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Visual C\+\+ предоставляет поддержку для создания многопоточных приложений в операционных системах Microsoft Windows: Windows XP, Windows 2000, Windows NT, Windows Me и Windows 98.  Возможно, потребуется использовать более одного потока, если приложению приходится управлять несколькими действиями, например одновременным вводом с клавиатуры и с помощью мыши.  Один поток может обрабатывать ввод с клавиатуры, в то время как второй поток фильтрует действия, выполненные с помощью мыши.  Третий поток может обновлять отображение на мониторе на основе данных, полученных из потоков обработки действий мыши и клавиатуры.  В то же время другие потоки могут обращаться к файлам на диске или получать данные из СОМ\-порта.  
  
 При использовании Visual C\+\+ существует два способа программирования многопоточных приложений: с использованием библиотеки Microsoft Foundation Class \(MFC\) или библиотеки времени выполнения на языке С и Win32 API.  Дополнительные сведения о создании многопоточных приложений с использованием библиотеки MFC см. в разделе [Реализация многопоточности на языке С \+\+ с помощью MFC](../parallel/multithreading-with-cpp-and-mfc.md) после ознакомления со следующими разделами, касающихся многопоточности на языке С.  
  
 В этих разделах описываются функции Visual C\+\+, поддерживающие создание многопоточных программ.  
  
## Дополнительные сведения  
  
-   [Что представляет собой многопоточность](../parallel/multithread-programs.md)  
  
-   [Поддержка многопоточности библиотеками](../parallel/library-support-for-multithreading.md)  
  
-   [Включаемые файлы для многопоточности](../parallel/include-files-for-multithreading.md)  
  
-   [Функции управления потоками в библиотеке времени выполнения на языке C](../parallel/c-run-time-library-functions-for-thread-control.md)  
  
-   [Пример многопоточной программы на языке С](../parallel/sample-multithread-c-program.md)  
  
-   [Написание многопоточной программы Win32](../Topic/Writing%20a%20Multithreaded%20Win32%20Program.md)  
  
-   [Компиляция и связывание многопоточных программ](../parallel/compiling-and-linking-multithread-programs.md)  
  
-   [Устранение потенциальных проблем при работе с многопоточными программами](../Topic/Avoiding%20Problem%20Areas%20with%20Multithread%20Programs.md)  
  
-   [Локальное хранилище потока \(TLS\)](../parallel/thread-local-storage-tls.md)  
  
## См. также  
 [Поддержка многопоточности для устаревшего кода \(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)