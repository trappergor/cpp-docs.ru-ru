---
title: "Серверы: Реализация документов сервера | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE server applications [MFC], managing server documents
- OLE server applications [MFC], implementing OLE servers
- servers, server documents
- server documents [MFC], implementing
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c4b8618e4951ac499d504cc68b0552ea45eed03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="servers-implementing-server-documents"></a>Серверы. Реализация документов сервера
В этой статье описаны шаги необходимо выполнить для успешной реализации серверного документа, если вы не указали параметр OLE-сервера в мастере приложений.  
  
#### <a name="to-define-a-server-document-class"></a>Для определения класса документов сервера  
  
1.  Создайте производный класс документа из `COleServerDoc` вместо **CDocument**.  
  
2.  Создайте класс server элемент, производный от `COleServerItem`.  
  
3.  Реализуйте `OnGetEmbeddedItem` функции-члена класса документа вашего сервера.  
  
     `OnGetEmbeddedItem`вызывается, если пользователь приложения контейнер создает или изменяет встроенного элемента. Она должна возвращать элемент, представляющий весь документ. Это должен быть объект вашей `COleServerItem`-производного класса.  
  
4.  Переопределить `Serialize` функции-члена для сериализации содержимого документа. Необходимо сериализовать список элементов сервера, если вы не используете их для представления данных в собственном в документе. Дополнительные сведения см. в разделе *реализации элементы сервера* в статье [серверов: элементы сервера](../mfc/servers-server-items.md).  
  
 При создании серверного документа, платформа автоматически регистрирует документа OLE системные библиотеки DLL. Это позволяет библиотеки DLL для поиска документов сервера.  
  
 Дополнительные сведения см. в разделе [COleServerItem](../mfc/reference/coleserveritem-class.md) и [COleServerDoc](../mfc/reference/coleserverdoc-class.md) в *Справочник по библиотеке классов*.  
  
## <a name="see-also"></a>См. также  
 [Серверы](../mfc/servers.md)   
 [Серверы: Элементы сервера](../mfc/servers-server-items.md)   
 [Серверы: Реализация сервера](../mfc/servers-implementing-a-server.md)   
 [Серверы. Реализация окон фрейма на месте](../mfc/servers-implementing-in-place-frame-windows.md)

