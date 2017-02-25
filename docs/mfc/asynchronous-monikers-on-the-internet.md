---
title: "Асинхронные моникеры в Интернете | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления ActiveX [C++], асинхронный"
  - "асинхронные моникеры [C++]"
  - "загрузка интернет-ресурсов и асинхронных моникеров"
  - "Интернет [C++], асинхронное скачивание"
  - "MFC [C++], асинхронные моникеры"
  - "оптимизация [C++], асинхронное скачивание в Интернете"
  - "веб-приложения [C++], асинхронный"
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Асинхронные моникеры в Интернете
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Интернет для новых подходами к разработке приложений, поскольку она медленного сетевого доступа.  Приложения должны работать сетевой доступ асинхронно, чтобы избежать заглохнуть интерфейс пользователя.  Класс MFC [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) предоставляет асинхронную поддержку загрузить файлы.  
  
 С асинхронными моникерами можно расширить приложение COM загрузить асинхронно через Интернет и предоставить прогрессивная отрисовка больших объектов, таких как растровые изображения и объекты VRML.  Асинхронные моникеры включают свойство элемента управления ActiveX или файл в Интернете, чтобы загрузить без блокировки ответ интерфейса пользователя.  
  
## Преимущества асинхронных моникеров  
 Можно использовать асинхронные моникеры:  
  
-   Код и файлы загрузки без блокировки.  
  
-   Свойства загрузки в элементах управления ActiveX без блокировки.  
  
-   Получение уведомлений о ходе выполнения загрузки.  
  
-   Отслеживание хода выполнения и готовности сведений о состоянии.  
  
-   Реализуйте сведения о состоянии пользователю сведения о ходе выполнения.  
  
-   Разрешить пользователю отменить загрузить в любое время.  
  
## Классы MFC для асинхронных моникеров  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) является производным от [CMonikerFile](../Topic/CMonikerFile%20Class.md), который, в свою очередь, наследуется от [COleStreamFile](../Topic/COleStreamFile%20Class.md).  Объект `COleStreamFile` представляет поток данных; объект `CMonikerFile` использует `IMoniker` для получения данных, и объект `CAsyncMonikerFile` делает ее асинхронно.  
  
 Асинхронные моникеры используются в основном в приложениях и включается для элементов управления ActiveX, отзывчивый интерфейс пользователя во время передачи файлов.  Блестящий примера можно использовать [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md) для асинхронных свойства элементов управления ActiveX.  
  
## Классы MFC для получения каналов в элементах управления ActiveX  
 Классы `CDataPathProperty` и MFC [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md) реализует свойства элемента управления ActiveX, которые могут быть загружены в асинхронном режиме.  Асинхронные свойства загружаются синхронного после запуска.  Асинхронные элементы управления ActiveX повторно вызывают обратный вызов, чтобы показать доступность новых данных во время длинномерного процесса обмена свойства.  
  
 `CDataPathProperty` является производным от `CAsyncMonikerFile`.  `CCachedDataPathProperty` является производным от `CDataPathProperty`.  Асинхронные реализации свойства в своих элементов управления ActiveX, производный от `CDataPathProperty` или `CCachedDataPathProperty` и переопределить [Ondataavailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md) и других уведомления, которую требуется получить.  
  
#### Загрузить файл, используя асинхронные моникеры  
  
1.  Объявите класс, производный от [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).  
  
2.  Переопределение [Ondataavailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md) для отображения данных.  
  
3.  Переопределите другие функции\-члены, включая [OnProgress](../Topic/CAsyncMonikerFile::OnProgress.md), [OnStartBinding](../Topic/CAsyncMonikerFile::OnStartBinding.md) и [OnStopBinding](../Topic/CAsyncMonikerFile::OnStopBinding.md).  
  
4.  Объявите экземпляр этого класса и использовать ее для открытия URL\-адреса.  
  
 Дополнительные сведения о загрузить асинхронно в элемент управления ActiveX см. в разделе [Элементы управления ActiveX в Интернете](../mfc/activex-controls-on-the-internet.md).  
  
## См. также  
 [Задачи программирования для интернет\-решений MFC](../mfc/mfc-internet-programming-tasks.md)   
 [Основы программирования для интернет\-решений MFC](../mfc/mfc-internet-programming-basics.md)