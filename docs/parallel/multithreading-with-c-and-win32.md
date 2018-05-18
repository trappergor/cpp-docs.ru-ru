---
title: Многопоточность с C и Win32 | Документы Microsoft
ms.custom: ''
ms.date: 02/02/2018
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows API [C++], multithreading
- multithreading [C++], C and Win32
- Visual C, multithreading
- Win32 applications [C++], multithreading
- threading [C++], C and Win32
- Win32 [C++], multithreading
- threading [C]
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 993bee92c9dacc831a8bbc8fc000ec982025a399
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="multithreading-with-c-and-win32"></a>Реализация многопоточности на языке C с помощью функций Win32
Microsoft Visual C++ поддерживает создание многопоточных приложений. Можно использовать более одного потока, если приложению для выполнения ресурсоемких операций, вызывающих пользовательского интерфейса перестанет отвечать.  
  
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