---
title: "Многопоточность с C и Win32 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows API [C++], multithreading
- multithreading [C++], C and Win32
- Visual C, multithreading
- Win32 applications [C++], multithreading
- threading [C++], C and Win32
- Win32 [C++], multithreading
- threading [C]
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 30c7833a4df80669b6223f1fe6b1ccceed0257cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-with-c-and-win32"></a>Реализация многопоточности на языке C с помощью функций Win32
Microsoft Visual C++ поддерживает создание многопоточных приложений с Microsoft Windows: Windows XP, Windows 2000, Windows NT, Windows Me и Windows 98. Можно использовать более одного потока, если приложению приходится управлять несколькими действиями, например одновременных клавиатуры и мыши. Один поток может обрабатывать ввод с клавиатуры, а второй поток фильтрует действия мыши. Третий поток можно обновить экран, на основе данных из потоков с помощью мыши и клавиатуры. В то же время другие потоки доступ к файлам на диске или получить данные из COM-портом.  
  
 С помощью Visual C++ существует два способа для программы с несколькими потоками: использование библиотеки Microsoft Foundation Class (MFC) или библиотеки времени выполнения C и Win32 API. Сведения о создании многопоточных приложений с MFC см. в разделе [многопоточность с помощью C++ и MFC](../parallel/multithreading-with-cpp-and-mfc.md) после считывания в следующих разделах о многопоточность на языке C.  
  
 В этих разделах приведены компоненты Visual C++, поддерживающие создание многопоточных программ.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Что многопоточность вскоре](../parallel/multithread-programs.md)  
  
-   [Поддержка библиотек для многопоточности](../parallel/library-support-for-multithreading.md)  
  
-   [Включаемые файлы для многопоточности](../parallel/include-files-for-multithreading.md)  
  
-   [Функции управления потоками в библиотеке времени выполнения C](../parallel/c-run-time-library-functions-for-thread-control.md)  
  
-   [Образец многопотоковой программы на языке C](../parallel/sample-multithread-c-program.md)  
  
-   [Написание многопоточной программы Win32](../parallel/writing-a-multithreaded-win32-program.md)  
  
-   [Компиляция и компоновка многопоточных программ](../parallel/compiling-and-linking-multithread-programs.md)  
  
-   [Устранение потенциальных проблем при работе с многопотоковыми программами](../parallel/avoiding-problem-areas-with-multithread-programs.md)  
  
-   [Локальное хранилище потока (TLS)](../parallel/thread-local-storage-tls.md)  
  
## <a name="see-also"></a>См. также  
 [Поддержка многопоточности для устаревшего кода (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)