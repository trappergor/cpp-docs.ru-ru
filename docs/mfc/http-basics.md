---
title: Основы HTTP | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTTP [MFC], return codes
- return codes [MFC]
- HTTP requests [MFC], return codes
ms.assetid: 5b7421bf-42c8-4f3a-8566-8ff5957f58cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56a2692edd9d41f80023e44f4ca8172cba8f9d00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="http-basics"></a>Основы HTTP
При написании веб-приложение, часто просмотрите и добавьте сведения в заголовке HTTP. Коды возврата указать на успех или сбой запрошенного события. В следующей таблице перечислены некоторые распространенные коды возврата.  
  
|Код возврата|Значение|  
|-----------------|-------------|  
|200|URL-адрес находится ниже передачи|  
|400|Нельзя расшифровать запрос|  
|404|Запрошенный URL-адрес не найден|  
|405|Сервер не поддерживает запрошенный метод|  
|500|Неизвестная ошибка сервера|  
|503|Служба недоступна|  
  
 HTTP-ответы, группируются, как показано в следующей таблице.  
  
|Группа|Значение|  
|-----------|-------------|  
|200-299|Success|  
|300-399|Сведения|  
|400-499|Ошибка запроса|  
|500-599|Ошибка сервера|  
  
 Протокол передачи гипертекста (HTTP) — это протокол уровня приложения для информационных гипермедиа-систем. Дополнительные сведения о HTTP и взаимодействия веб-браузеров и серверов см. в спецификации протокола передачи гипертекста (HTTP):  
  
 [http://www.w3.org/pub/WWW/Protocols/](http://www.w3.org/pub/www/protocols/)  
  
## <a name="see-also"></a>См. также  
 [Основы программирования для интернет-решений MFC](../mfc/mfc-internet-programming-basics.md)

