---
title: Реализация многопоточности на языке C с помощью функций Win32 | Документация Майкрософт
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
ms.openlocfilehash: 8dc9569457b6726aee18359a7ff74e9a45873deb
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2018
ms.locfileid: "42538514"
---
# <a name="multithreading-with-c-and-win32"></a>Реализация многопоточности на языке C с помощью функций Win32
Microsoft Visual C++ предоставляет поддержку для создания многопоточных приложений. Можно использовать более одного потока, если приложению для выполнения ресурсоемких операций, которые могут привести пользовательский интерфейс перестанет отвечать на запросы.  
  
С помощью Visual C++, существует два способа программирования многопоточных: использование библиотеки Microsoft Foundation Class (MFC) или библиотеки времени выполнения C и Win32 API. Сведения о создании многопоточных приложений с MFC, см. в разделе [многопоточность с помощью C++ и MFC](../parallel/multithreading-with-cpp-and-mfc.md) после ознакомления со следующими разделами, касающихся многопоточности на языке C.  
  
В этих разделах описываются функции Visual C++, поддерживающие создание многопоточных программ.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
- [Что многопоточность посвящен](../parallel/multithread-programs.md)  
  
- [Поддержка библиотек для многопоточности](../parallel/library-support-for-multithreading.md)  
  
- [Включаемые файлы для многопоточности](../parallel/include-files-for-multithreading.md)  
  
- [Функции управления потоками в библиотеке времени выполнения C](../parallel/c-run-time-library-functions-for-thread-control.md)  
  
- [Пример многопоточной программы на C](../parallel/sample-multithread-c-program.md)  
  
- [Написание многопоточной программы Win32](../parallel/writing-a-multithreaded-win32-program.md)  
  
- [Компиляция и компоновка многопоточных программ](../parallel/compiling-and-linking-multithread-programs.md)  
  
- [Устранение потенциальных проблем с многопоточными программами](../parallel/avoiding-problem-areas-with-multithread-programs.md)  
  
- [Локальное хранилище потока (TLS)](../parallel/thread-local-storage-tls.md)  
  
## <a name="see-also"></a>См. также  
 
[Поддержка многопоточности для устаревшего кода (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)