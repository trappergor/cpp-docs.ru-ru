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
ms.openlocfilehash: 09397b5a60dcc2cbe2b3e6265f6080f3c5c1e212
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428100"
---
# <a name="multithreading-with-c-and-win32"></a>Реализация многопоточности на языке C с помощью функций Win32

Microsoft Visual C++ предоставляет поддержку для создания многопоточных приложений. Можно использовать более одного потока, если приложению для выполнения ресурсоемких операций, которые могут привести пользовательский интерфейс перестанет отвечать на запросы.

С помощью Visual C++, существует два способа программирования многопоточных: использование библиотеки Microsoft Foundation Class (MFC) или библиотеки времени выполнения C и Win32 API. Сведения о создании многопоточных приложений с MFC, см. в разделе [многопоточность с помощью C++ и MFC](multithreading-with-cpp-and-mfc.md) после ознакомления со следующими разделами, касающихся многопоточности на языке C.

В этих разделах описываются функции Visual C++, поддерживающие создание многопоточных программ.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Что многопоточность посвящен](multithread-programs.md)

- [Поддержка библиотек для многопоточности](library-support-for-multithreading.md)

- [Включаемые файлы для многопоточности](include-files-for-multithreading.md)

- [Функции управления потоками в библиотеке времени выполнения C](c-run-time-library-functions-for-thread-control.md)

- [Пример многопоточной программы на C](sample-multithread-c-program.md)

- [Написание многопоточной программы Win32](writing-a-multithreaded-win32-program.md)

- [Компиляция и компоновка многопоточных программ](compiling-and-linking-multithread-programs.md)

- [Устранение потенциальных проблем с многопоточными программами](avoiding-problem-areas-with-multithread-programs.md)

- [Локальное хранилище потока (TLS)](thread-local-storage-tls.md)

## <a name="see-also"></a>См. также

[Поддержка многопоточности для устаревшего кода (Visual C++)](multithreading-support-for-older-code-visual-cpp.md)