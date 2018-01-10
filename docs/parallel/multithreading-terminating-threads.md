---
title: ": Многопоточность | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CREATE_SUSPENDED
dev_langs: C++
helpviewer_keywords:
- premature thread termination
- starting threads
- threading [MFC], terminating threads
- multithreading [C++], terminating threads
- threading [C++], stopping threads
- terminating threads
- stopping threads
- AfxEndThread method
ms.assetid: 4c0a8c6d-c02f-456d-bd02-0a8c8d006ecb
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8017d47f632374d8979d9a0850e1d1bfd8b9df07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-terminating-threads"></a>Многопоточность. Завершение потоков
Завершение потока, может произойти двух случаях: контролирующей функции или поток не разрешено выполняться до завершения. Если текстовый процессор поток для печати в фоновом режиме, функция управления завершается при успешном выполнении задания печати. Если пользователю необходимо отменить печать, однако печати фоновый поток должен быть преждевременно. В этом разделе объясняется, как реализовать каждой ситуации и как получить код выхода потока после его завершения.  
  
-   [Обычное завершение потока](#_core_normal_thread_termination)  
  
-   [Преждевременное завершение потока](#_core_premature_thread_termination)  
  
-   [Получение кода выхода из потока](#_core_retrieving_the_exit_code_of_a_thread)  
  
##  <a name="_core_normal_thread_termination"></a>Обычное завершение потока  
 Для рабочего потока, обычное завершение потока является простым: выхода из функции управления и возврата значением, указывающим причину завершения. Можно использовать любой [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) функции или `return` инструкции. Как правило 0 означает успешное выполнение, но это вы сами.  
  
 Пользовательский интерфейс происходит так же просто: из потока пользовательского интерфейса, вызовите [функцию PostQuitMessage](http://msdn.microsoft.com/library/windows/desktop/ms644945) в [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]. Единственный параметр, **функцию PostQuitMessage** принимает — это код выхода потока. Как и для рабочих потоков 0 обычно означает успешное завершение.  
  
##  <a name="_core_premature_thread_termination"></a>Преждевременное завершение потока  
 Преждевременное завершение потока выполняется почти так же просто: вызов [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) из потока. Передайте необходимый код выхода в качестве единственного параметра. Это останавливает выполнение потока, освобождает стека потока, отсоединяет все библиотеки DLL, присоединенный к потоку и удаляет объект потока из памяти.  
  
 `AfxEndThread`должна вызываться из потока, подлежащего прерыванию. Если вы хотите завершить поток из другого потока, необходимо настроить способ связи между двумя потоками.  
  
##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a>Получение кода выхода из потока  
 Чтобы получить код выхода или потока пользовательского интерфейса, вызовите [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190) функции. Сведения об этой функции см. в разделе [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]. Эта функция принимает дескриптор потока (хранятся в `m_hThread` данными-членом `CWinThread` объектов) и адрес `DWORD`.  
  
 Если поток по-прежнему активна, **GetExitCodeThread** помещает **STILL_ACTIVE** в предоставленном `DWORD` адрес; в противном случае код завершения помещается в этот адрес.  
  
 Получение кода выхода из [CWinThread](../mfc/reference/cwinthread-class.md) объекты необходимо выполнить дополнительное действие. По умолчанию когда `CWinThread` завершения потока, удаляется объект потока. Это означает, что не удается получить доступ к `m_hThread` элемент данных из-за `CWinThread` объект больше не существует. Чтобы избежать такой ситуации, выполните одно из следующих действий.  
  
-   Задать `m_bAutoDelete` данные-члены **FALSE**. Это позволяет `CWinThread` объекта после завершения потока. Теперь можно получить доступ к `m_hThread` член данных после завершения потока. При использовании этого метода, однако, вы несете ответственность за уничтожение `CWinThread` объекта, так как платформа не выполнит удаление автоматически. Это предпочтительный метод.  
  
-   Дескриптор потока следует храните отдельно. После создания потока, скопировать его `m_hThread` данные-член (с помощью **:: DuplicateHandle**) в другую переменную и доступ к нему через эту переменную. Таким образом, объект автоматически удаляется при завершении и можно по-прежнему выяснить, почему поток остановлен. Будьте внимательны, что поток до завершения можно дублировать дескриптор. Наиболее безопасным способом для этого является передача **CREATE_SUSPENDED** для [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), хранящие дескриптор и возобновить поток путем вызова [ResumeThread](../topic/../mfc/reference/cwinthread-class.md#resumethread).  
  
 Оба этих метода позволяет определить, почему `CWinThread` завершения объекта.  
  
## <a name="see-also"></a>См. также  
 [Реализация многопоточности на C++ с MFC](../parallel/multithreading-with-cpp-and-mfc.md)   
 [_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)   
 [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659)