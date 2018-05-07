---
title: Приложения и поток поддерживают классы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.support
dev_langs:
- C++
helpviewer_keywords:
- application objects [MFC], thread support classes
- lock classes [MFC]
- thread support classes [MFC]
- threading [MFC]
- synchronization classes [MFC], multithreading
- application support classes [MFC]
ms.assetid: 3c1d14fd-c35c-48f1-86ce-1e0f9a32c36d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9f3877cf85e369756b15d565af1481fd6d258df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="application-and-thread-support-classes"></a>Классы поддержки приложений и потоков
Каждое приложение имеет только один объект приложения; Этот объект координирует других объектов в работающей программе и является производным от `CWinApp`.  
  
 Библиотека Microsoft Foundation Class (MFC) поддерживает несколько потоков выполнения в приложении. Все приложения должны иметь по крайней мере один поток; поток, используемый вашей `CWinApp` объект является этот основной поток.  
  
 `CWinThread` Инкапсулирует часть возможностей потоков операционной системы. Чтобы сделать использование нескольких потоков, MFC также предоставляет синхронизации классы объектов для предоставления интерфейса C++ объектов синхронизации Win32.  
  
## <a name="application-and-thread-classes"></a>Классы приложений и потоков  
 [CWinApp](../mfc/reference/cwinapp-class.md)  
 Инкапсулирует код для инициализации, запуска и завершения работы приложения. Объект приложения будет наследовать от этого класса.  
  
 [CWinThread](../mfc/reference/cwinthread-class.md)  
 Базовый класс для всех потоков. Использовать непосредственно или являются производными от класса `CWinThread` Если поток выполняет функции пользовательского интерфейса. Класс `CWinApp` является производным от `CWinThread`.  
  
## <a name="synchronization-object-classes"></a>Классы синхронизации объектов  
 [CSyncObject](../mfc/reference/csyncobject-class.md)  
 Базовый класс для классов объектов синхронизации.  
  
 [CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
 Класс синхронизации, который позволяет только один поток в пределах одного процесса для доступа к объекту.  
  
 [CSemaphore](../mfc/reference/csemaphore-class.md)  
 Класс синхронизации, который позволяет от одного до указанное максимальное количество одновременных доступов к объекту.  
  
 [CMutex](../mfc/reference/cmutex-class.md)  
 Класс синхронизации, который позволяет только один поток в любое количество процессов, для доступа к объекту.  
  
 [CEvent](../mfc/reference/cevent-class.md)  
 Класс синхронизации, который сообщает приложению, когда произошло событие.  
  
 [Класс CSingleLock](../mfc/reference/csinglelock-class.md)  
 Использовать в функции-члены потокобезопасные классы блокировки на один объект синхронизации.  
  
 [CMultiLock](../mfc/reference/cmultilock-class.md)  
 Использовать в функции-члены потокобезопасные классы блокировки на один или несколько объектов синхронизации в массиве объектов синхронизации.  
  
## <a name="related-classes"></a>Связанные классы  
 [CCommandLineInfo](../mfc/reference/ccommandlineinfo-class.md)  
 Выполняет синтаксический анализ командной строки, с которой запущена программа.  
  
 [CWaitCursor](../mfc/reference/cwaitcursor-class.md)  
 Помещает курсор ожидания на экране. Используется во время длительных операций.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 Обрабатывает постоянное хранилище для закрепления данные о состоянии для панели элементов управления.  
  
 [CRecentFileList](../mfc/reference/crecentfilelist-class.md)  
 Сохраняет последние использовавшиеся списка файлов (MRU).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

