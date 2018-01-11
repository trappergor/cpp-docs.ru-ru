---
title: "Тестирование Интернет-приложений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Web applications [MFC], testing
- debugging Web applications [MFC], testing applications
- testing [MFC], Internet applications
- debugging [MFC], Web applications
- Internet debugging and testing
ms.assetid: ac4c74e3-d4ad-4e19-8f6c-e270de067f01
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0cc214eb98b8aa9e927fd471ba313e4cade426a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="testing-internet-applications"></a>Тестирование интернет-приложений
Существуют некоторые уникальные задачи тестирования в Интернете, особенно для приложений, выполняющихся на веб-сервере. Первоначального тестирования, возможно, выполняются с помощью клиента одного пользователя, подключающегося к на тестовом сервере. Это будет полезна для отладки кода.  
  
 Необходимо также проверить в реальных условиях: с нескольких клиентов, подключенных через высокоскоростных соединений, а также низкоскоростных последовательных линий, включая подключения модема. Он может быть трудно имитации реальных условиях, но определенно стоит тратить время проектирование возможные сценарии и выполнять их. Если это возможно также может потребоваться использовать инструменты для выполнения емкости и нагрузочное тестирование. Определенные классы ошибок, такие как ошибки истечения времени трудны для поиска и воспроизведения.  
  
 Одна из сложностей, связанных с Интернет-программирование — его видимость. Много обращений к веб-узла может замедлить сервера. Ваш сервер должен завершаться. Требуется запретить все, что может быть разрушительных на компьютере пользователя, при сбое приложения (например, повреждение данных при записи в реестр или при записи файлов cookie на стороне клиента).  
  
## <a name="see-also"></a>См. также  
 [Задачи программирования для Интернет MFC](../mfc/mfc-internet-programming-tasks.md)   
 [Основы программирования для интернет-решений MFC](../mfc/mfc-internet-programming-basics.md)

