---
title: "Многопоточность: Использование классов синхронизации | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [MFC], synchronization classes
- resources [C++], multithreading
- synchronization classes [C++]
- synchronization [C++], multithreading
- controlled resource access [C++]
- synchronization access classes [C++]
- threading [C++], synchronization
- multithreading [C++], synchronization classes
ms.assetid: 4914f54e-68ac-438f-93c9-c013455a657e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 38437983552dfdf2cf6708ec5fd067e06387ea5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-when-to-use-the-synchronization-classes"></a>Многопоточность. Использование классов синхронизации
Многопоточные классов, предоставляемых с MFC делятся на две категории: объекты синхронизации ([CSyncObject](../mfc/reference/csyncobject-class.md), [CSemaphore](../mfc/reference/csemaphore-class.md), [CMutex](../mfc/reference/cmutex-class.md), [ CCriticalSection](../mfc/reference/ccriticalsection-class.md), и [CEvent](../mfc/reference/cevent-class.md)) и синхронизации доступа к объектам ([CMultiLock](../mfc/reference/cmultilock-class.md) и [класс CSingleLock](../mfc/reference/csinglelock-class.md)).  
  
 Классы синхронизации используются, когда необходимо контролировать доступ к ресурсу для обеспечения целостности ресурса. Классы синхронного доступа используются для получения доступа к контролируемым ресурсам. В этом разделе приводится описание использования каждого класса.  
  
 Чтобы определить, какой класс синхронизации, следует использовать, ответьте на следующие вопросы:  
  
1.  Приложения необязательно будет ожидать, что-то происходит перед предоставлением доступа к ресурсу (например, данные должны быть получены из COM-портом перед записью в файл)?  
  
     Если Да, использовать `CEvent`.  
  
2.  Можно более одного потока в один и тот же уровень доступа приложения этого ресурса за один раз (например, приложение позволяет до пяти windows с представлениями в том же документе)?  
  
     Если Да, использовать `CSemaphore`.  
  
3.  Более одного приложения можно использовать этот ресурс (например, ресурс находится в библиотеке DLL)?  
  
     Если Да, использовать `CMutex`.  
  
     Если нет, используйте `CCriticalSection`.  
  
 **CSyncObject** никогда не используется напрямую. Это базовый класс для четырех других классов синхронизации.  
  
## <a name="example-1-using-three-synchronization-classes"></a>Пример 1: Использование трех классов синхронизации  
 Например рассмотрим приложение, поддерживающее связанный список учетных записей. Это приложение позволяет проверять в отдельных окнах до трех учетных записей, но можно обновить в любой конкретный момент времени только один. При обновлении учетной записи обновленные данные отправляются по сети в архив данных.  
  
 В этом примере приложения используются все три типа классов синхронизации. Так как до трех учетных записей за один раз, используется `CSemaphore` для ограничения доступа к трем объектам просмотра. При попытке просмотра четвертой учетной записи приложение находится в ожидании закрытия одного из первых трех окон или завершается с ошибкой. При обновлении учетной записи приложение использует `CCriticalSection` чтобы убедиться, что только одна учетная запись обновляется одновременно. После успешного обновления сообщает `CEvent`, который освобождает поток, ожидающий отслеживаемого события. Этот поток отправляет новые данные в архив данных.  
  
## <a name="example-2-using-synchronization-access-classes"></a>Пример 2: Использование классов синхронизации доступа к  
 Выбор используемого класса доступа синхронизации для использования стало еще проще. Если приложение отвечает за доступ к отдельному управляемому ресурсу только, используйте `CSingleLock`. Если требуется доступ к одному из нескольких управляемых ресурсов, используйте `CMultiLock`. В примере 1 `CSingleLock` был бы использован, поскольку в каждом случае требуется только один ресурс в любой конкретный момент времени.  
  
 Сведения об использовании классов синхронизации см. в разделе [Многопоточность: использование классов синхронизации](../parallel/multithreading-how-to-use-the-synchronization-classes.md). Сведения о синхронизации см. в разделе [синхронизации](http://msdn.microsoft.com/library/windows/desktop/ms686353) в [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]. Сведения о поддержке многопоточности в MFC см. в разделе [многопоточность с помощью C++ и MFC](../parallel/multithreading-with-cpp-and-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [Реализация многопоточности на языке C++ с помощью классов MFC](../parallel/multithreading-with-cpp-and-mfc.md)