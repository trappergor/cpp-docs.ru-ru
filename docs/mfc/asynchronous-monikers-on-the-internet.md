---
title: "Асинхронные моникеры в Интернете | Документы Microsoft"
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
- ActiveX controls [MFC], asynchronous
- MFC, asynchronous monikers
- asynchronous monikers [MFC]
- Web applications [MFC], asynchronous
- downloading Internet resources and asynchronous monikers
- optimization [MFC], asynchronous downloading across Internet
- Internet [MFC], asynchronous downloading
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cd7b6be66c3049c1d82aa549cf362a840fd6f265
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="asynchronous-monikers-on-the-internet"></a>Асинхронные моникеры в Интернете
Интернет требуется нового подхода к разработке приложения из-за его доступ к медленной сети. Приложения должны выполнять доступ к сети асинхронно, чтобы избежать остановился пользовательского интерфейса. Класс MFC [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) обеспечивает асинхронную реализацию, для загрузки файлов.  
  
 Асинхронные моникеры расширить COM-приложения для загрузки асинхронно через Интернет и предоставить последовательную отрисовку больших объектов, таких как растровые изображения и VRML объектов. Асинхронные моникеры включить свойство элемента управления ActiveX или файла в Интернете для загрузки без блокировки отклика пользовательского интерфейса.  
  
## <a name="advantages-of-asynchronous-monikers"></a>Преимущества асинхронных моникеров  
 Можно использовать асинхронные моникеры для:  
  
-   Загрузите файлы кода и без блокировки.  
  
-   Загрузка свойств элементов управления ActiveX без блокировки.  
  
-   Получение уведомлений о загрузке хода выполнения.  
  
-   Отслеживание хода выполнения и сведения о состоянии готовности.  
  
-   Предоставляют сведения о состоянии для пользователя о ходе выполнения.  
  
-   Разрешить пользователю отменить загрузку в любое время.  
  
## <a name="mfc-classes-for-asynchronous-monikers"></a>Классы MFC для асинхронных моникеров  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) является производным от [CMonikerFile](../mfc/reference/cmonikerfile-class.md), который в свою очередь является производным от [COleStreamFile](../mfc/reference/colestreamfile-class.md). Объект `COleStreamFile` объект представляет поток данных; с помощью `CMonikerFile` объектов используют `IMoniker` для получения данных и `CAsyncMonikerFile` объекта выполняется асинхронно.  
  
 Асинхронные моникеры используются главным образом в Интернет-приложений и элементов управления ActiveX для обеспечения быстрого реагирования пользовательского интерфейса во время передачи файлов. Простым примером этого является использование [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md) для предоставления асинхронных свойств для элементов управления ActiveX.  
  
## <a name="mfc-classes-for-data-paths-in-activex-controls"></a>Классы MFC для пути к данным в элементах управления ActiveX  
 Классы MFC `CDataPathProperty` и [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md) реализации свойства элемента управления ActiveX, которые могут быть загружены асинхронно. Асинхронные свойства загружаются после синхронного запуска. Асинхронные элементы управления ActiveX многократно вызывать обратный вызов для указания доступности новых данных появляется в процессе обмена свойство длительное время.  
  
 Класс `CDataPathProperty` является производным от `CAsyncMonikerFile`. Класс `CCachedDataPathProperty` является производным от `CDataPathProperty`. Для реализации асинхронных свойств элементов управления ActiveX, создайте класс, производный от `CDataPathProperty` или `CCachedDataPathProperty`и Переопределите [OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable) и других уведомлений, которые вы хотите получать.  
  
#### <a name="to-download-a-file-using-asynchronous-monikers"></a>Чтобы загрузить файл с помощью асинхронных моникеров  
  
1.  Объявите класс, производный от [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).  
  
2.  Переопределить [OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable) для отображения данных.  
  
3.  Переопределить других функций-членов, включая [OnProgress](../mfc/reference/casyncmonikerfile-class.md#onprogress), [OnStartBinding](../mfc/reference/casyncmonikerfile-class.md#onstartbinding), и [OnStopBinding](../mfc/reference/casyncmonikerfile-class.md#onstopbinding).  
  
4.  Объявите экземпляр этого класса и использовать ее для открытия URL-адреса.  
  
 Сведения о загрузке асинхронно в элементе управления ActiveX см. в разделе [элементы управления ActiveX в Интернете](../mfc/activex-controls-on-the-internet.md).  
  
## <a name="see-also"></a>См. также  
 [Задачи программирования для Интернет MFC](../mfc/mfc-internet-programming-tasks.md)   
 [Основы программирования для интернет-решений MFC](../mfc/mfc-internet-programming-basics.md)

