---
title: 'Реализация многопоточности на языке: Завершение потоков в MFC'
ms.date: 08/27/2018
f1_keywords:
- CREATE_SUSPENDED
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
ms.openlocfilehash: dd11f5db646e172d7ea2c2cc646841249d95ef31
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303635"
---
# <a name="multithreading-terminating-threads-in-mfc"></a>Реализация многопоточности на языке: Завершение потоков в MFC

Завершение потока вызвать двух случаях: контролирующей функции или поток не разрешено выполняться до завершения. При использовании текстовым процессором потока для печати в фоновом режиме функцию управления завершается при успешном выполнении задания печати. Если пользователю необходимо отменить печать, однако фоновый поток печати должен быть преждевременно. В этом разделе объясняется, как реализовать каждой ситуации и способы получения кода выхода из потока после его завершения.

- [Обычное завершение потока](#_core_normal_thread_termination)

- [Преждевременное завершение потока](#_core_premature_thread_termination)

- [Извлечение кода выхода потока](#_core_retrieving_the_exit_code_of_a_thread)

##  <a name="_core_normal_thread_termination"></a> Обычное завершение потока

Для рабочего потока обычное завершение потока прост: Завершить контролирующую функцию и возвращает значение, обозначающее причину завершения. Можно использовать либо [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) функции или **возвращают** инструкции. Как правило 0 означает успешное выполнение, но это вы.

Поток пользовательского интерфейса происходит так же просто: из в UI-потоке, вызвать [PostQuitMessage](/windows/desktop/api/winuser/nf-winuser-postquitmessage) в пакете Windows SDK. Единственным параметром, `PostQuitMessage` — это код выхода из потока. Как и для рабочих потоков 0 обычно означает успешное завершение.

##  <a name="_core_premature_thread_termination"></a> Преждевременное завершение потока

Преждевременное завершение потока выполняется почти так же просто: Вызовите [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) из внутри потока. Передайте необходимый код выхода в качестве единственного параметра. Это останавливает выполнение потока, освобождает стек потока, отключению всех библиотек DLL, присоединенный к потоку и удалению объекта потока из памяти.

`AfxEndThread` Должен вызываться из потока, подлежащего прерыванию. Если вы хотите завершить поток из другого потока, необходимо настроить способ связи между двумя потоками.

##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a> Извлечение кода выхода потока

Чтобы получить код выхода из рабочего потока или потока пользовательского интерфейса, вызовите [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread) функции. Сведения об этой функции см. в разделе Windows SDK. Эта функция принимает дескриптор потока (хранящиеся в `m_hThread` данными-членом `CWinThread` объекты) и адрес DWORD.

Если поток по-прежнему активна, `GetExitCodeThread` помещает STILL_ACTIVE в предоставленный адрес DWORD; в противном случае код завершения помещается в этот адрес.

Извлечение кода выхода из [CWinThread](../mfc/reference/cwinthread-class.md) объектов необходимо выполнить дополнительное действие. По умолчанию когда `CWinThread` завершения потока, удаляется объект потока. Это означает, что при отсутствии доступа к `m_hThread` данные-член так как `CWinThread` объект больше не существует. Чтобы избежать такой ситуации, выполните одно из следующих действий.

- Задайте `m_bAutoDelete` элемент данных в значение FALSE. Это позволяет `CWinThread` объекта после завершения потока. Вы можете обращаться к `m_hThread` элемент данных после завершения потока. Если вы используете этот способ, тем не менее, вы несете ответственность за уничтожение `CWinThread` объекта, так как платформа не выполнит удаление автоматически. Это предпочтительный метод.

- Store дескриптор потока отдельно. После создания потока скопируйте его `m_hThread` данные-член (с помощью `::DuplicateHandle`) в другую переменную и доступ к нему через эту переменную. Таким образом, объект автоматически удаляется при, хотя вы можете узнать причину поток остановлен. Будьте внимательны, что поток до завершения можно дублировать дескриптор. Наиболее безопасным способом сделать это является передача CREATE_SUSPENDED для [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), сохранение дескриптора и затем возобновление потока путем вызова [ResumeThread](../mfc/reference/cwinthread-class.md#resumethread).

Каждый из этих методов позволяет определить, почему `CWinThread` завершения объекта.

## <a name="see-also"></a>См. также

[Реализация многопоточности на языке C++ с помощью классов MFC](multithreading-with-cpp-and-mfc.md)<br/>
[_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)<br/>
[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)<br/>
[ExitThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitthread)
