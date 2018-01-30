---
title: "Поддержка многопоточности для устаревшего кода (Visual C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- threading [C++]
- multiple threads
- concurrent programming [C++]
- programming [C++], multithreaded
- multithreading [C++], about multithreading
- multiple concurrent threads
- multithreading [C++]
ms.assetid: 24425b1f-5031-4c6b-aac7-017115a40e7c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e082fd9c3f4c34c97f461a11dcec14d778affd8
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2018
---
# <a name="multithreading-support-for-older-code-visual-c"></a>Поддержка многопоточности для устаревшего кода (Visual C++)
Visual C++ позволяет иметь несколько параллельных потоков выполнения, работающих одновременно. С помощью многопоточности можно выполнять фоновые задачи, управлять одновременных потоков ввода, управления пользовательского интерфейса и многое другое.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Реализация многопоточности на языке C с помощью функций Win32](../parallel/multithreading-with-c-and-win32.md)  
 Предоставляет поддержку для создания многопоточных приложений в Microsoft Windows  
  
 [Реализация многопоточности на языке C++ с помощью классов MFC](../parallel/multithreading-with-cpp-and-mfc.md)  
 Описывает процессы и потоки, и подход к MFC многопоточность является.  
  
 [Многопоточность и языковые стандарты](../parallel/multithreading-and-locales.md)  
 Описывает проблемы, возникающие при использовании функций языковых стандартов библиотеки времени выполнения C и стандартной библиотеки C++ в многопоточных приложениях.  
  
## <a name="related-sections"></a>Связанные разделы  
 [CWinThread](../mfc/reference/cwinthread-class.md)  
 Класс, представляющий поток исполнения в приложении.  
  
 [CSyncObject](../mfc/reference/csyncobject-class.md)  
 Описывает чисто виртуальный класс, обеспечивающий общую функциональность объектов синхронизации в Win32.  
  
 [CSemaphore](../mfc/reference/csemaphore-class.md)  
 Представляет семафор — объект синхронизации, позволяющий ограниченному числу потоков в один или несколько процессов, доступ к ресурсу.  
  
 [CMutex](../mfc/reference/cmutex-class.md)  
 Класс представляет мьютекс — объект синхронизации, позволяющий ограничить доступ к ресурсу одним потоком.  
  
 [CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
 Представляет критическую секцию — объект синхронизации, позволяющий одному потоку за раз, чтобы получить доступ к определенному фрагменту кода.  
  
 [CEvent](../mfc/reference/cevent-class.md)  
 Представляет событие, которое представляет собой объект синхронизации, который позволяет одному потоку известить другой, произошло событие.  
  
 [CMultiLock](../mfc/reference/cmultilock-class.md)  
 Класс представляет механизм контроля доступа к ресурсам в многопоточных программах.  
  
 [CSingleLock](../mfc/reference/csinglelock-class.md)  
 Класс представляет механизм контроля доступа к определенному ресурсу в многопоточных программах.  
