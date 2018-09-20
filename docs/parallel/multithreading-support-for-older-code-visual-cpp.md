---
title: Поддержка многопоточности для устаревшего кода (Visual C++) | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-parallel
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04767bfea727e32fb49d202358127685d9d5d2d0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421132"
---
# <a name="multithreading-support-for-older-code-visual-c"></a>Поддержка многопоточности для устаревшего кода (Visual C++)

Visual C++ позволяет иметь несколько параллельных потоков выполнения, работающих одновременно. С помощью многопоточности можно выполнять фоновые задачи, управлять одновременными потоками ввода, управления пользовательского интерфейса и многое другое.

## <a name="in-this-section"></a>В этом разделе

[Реализация многопоточности на языке C с помощью функций Win32](multithreading-with-c-and-win32.md)<br/>
Предоставляет поддержку для создания многопоточных приложений в Microsoft Windows

[Реализация многопоточности на языке C++ с помощью классов MFC](multithreading-with-cpp-and-mfc.md)<br/>
Описывает процессы и потоки, и подход MFC к многопоточности является.

[Многопоточность и языковые стандарты](multithreading-and-locales.md)<br/>
Описывает проблемы, возникающие при использовании функций языковых стандартов библиотеки времени выполнения C и стандартной библиотеки C++ в многопоточных приложениях.

## <a name="related-sections"></a>Связанные разделы

[CWinThread](../mfc/reference/cwinthread-class.md)<br/>
Класс, представляющий поток исполнения в приложении.

[CSyncObject](../mfc/reference/csyncobject-class.md)<br/>
Описывает чисто виртуальный класс, предоставляющий функции, общие для объектов синхронизации Win32.

[CSemaphore](../mfc/reference/csemaphore-class.md)<br/>
Класс представляет семафор — объект синхронизации, позволяющий ограниченному числу потоков в один или несколько процессах осуществлять доступ к ресурсу.

[CMutex](../mfc/reference/cmutex-class.md)<br/>
Класс представляет мьютекс — объект синхронизации, позволяющий ограничить доступ к ресурсу одним потоком.

[CCriticalSection](../mfc/reference/ccriticalsection-class.md)<br/>
Представляет критическую секцию — объект синхронизации, позволяющий одному потоку за раз, чтобы получить доступ к ресурсу или раздел кода.

[CEvent](../mfc/reference/cevent-class.md)<br/>
Представляет событие, которое — объект синхронизации, позволяющий одному потоку известить другой, что произошло событие поток.

[CMultiLock](../mfc/reference/cmultilock-class.md)<br/>
Класс представляет механизм контроля доступа к ресурсам в многопоточных программах.

[Класс CSingleLock](../mfc/reference/csinglelock-class.md)<br/>
Класс представляет механизм контроля доступа к определенному ресурсу в многопоточных программах.