---
title: 'Серверы: Реализация документов сервера | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE server applications [MFC], managing server documents
- OLE server applications [MFC], implementing OLE servers
- servers, server documents
- server documents [MFC], implementing
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 273fd1e5afefb8a10b3e1ae8e3c2f81ccec05e7f
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950832"
---
# <a name="servers-implementing-server-documents"></a>Серверы. Реализация документов сервера
В этой статье описаны шаги необходимо выполнить для успешной реализации серверного документа, если вы не указали параметр OLE-сервера в мастере приложений.  
  
#### <a name="to-define-a-server-document-class"></a>Для определения класса документов сервера  
  
1.  Создайте производный класс документа из `COleServerDoc` вместо `CDocument`.  
  
2.  Создайте класс server элемент, производный от `COleServerItem`.  
  
3.  Реализуйте `OnGetEmbeddedItem` функции-члена класса документа вашего сервера.  
  
     `OnGetEmbeddedItem` вызывается, если пользователь приложения контейнер создает или изменяет встроенного элемента. Она должна возвращать элемент, представляющий весь документ. Это должен быть объект вашей `COleServerItem`-производного класса.  
  
4.  Переопределить `Serialize` функции-члена для сериализации содержимого документа. Необходимо сериализовать список элементов сервера, если вы не используете их для представления данных в собственном в документе. Дополнительные сведения см. в разделе *реализации элементы сервера* в статье [серверов: элементы сервера](../mfc/servers-server-items.md).  
  
 При создании серверного документа, платформа автоматически регистрирует документа OLE системные библиотеки DLL. Это позволяет библиотеки DLL для поиска документов сервера.  
  
 Дополнительные сведения см. в разделе [COleServerItem](../mfc/reference/coleserveritem-class.md) и [COleServerDoc](../mfc/reference/coleserverdoc-class.md) в *Справочник по библиотеке классов*.  
  
## <a name="see-also"></a>См. также  
 [Серверы](../mfc/servers.md)   
 [Серверы: Элементы сервера](../mfc/servers-server-items.md)   
 [Серверы: Реализация сервера](../mfc/servers-implementing-a-server.md)   
 [Серверы. Реализация окон фрейма на месте](../mfc/servers-implementing-in-place-frame-windows.md)

