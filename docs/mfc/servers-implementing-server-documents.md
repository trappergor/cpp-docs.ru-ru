---
title: 'серверы: Реализация документов сервера'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], managing server documents
- OLE server applications [MFC], implementing OLE servers
- servers, server documents
- server documents [MFC], implementing
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
ms.openlocfilehash: 17ced1cdb0b40b13fbda68150030efde5735ba7b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261873"
---
# <a name="servers-implementing-server-documents"></a>серверы: Реализация документов сервера

Здесь объясняются шаги, которые необходимо выполнить для успешной реализации серверного документа, если не был указан параметр OLE-сервера в мастере приложений.

#### <a name="to-define-a-server-document-class"></a>Для определения класса документов сервера

1. Наследование класса документов от `COleServerDoc` вместо `CDocument`.

1. Создание сервера элемента класса, производного от `COleServerItem`.

1. Реализуйте `OnGetEmbeddedItem` функция-член класса документа сервера.

   `OnGetEmbeddedItem` вызывается, когда пользователь приложения контейнер создает или изменяет внедренного элемента. Она должна вернуть элемент, представляющий весь документ. Это должен быть объект вашей `COleServerItem`-производного класса.

1. Переопределить `Serialize` функция-член для сериализации содержимого документа. Необходимо сериализовать список элементов сервера, если вы не используете их для представления собственных данных в документе. Дополнительные сведения см. в разделе *элементы реализации сервера* в этой статье [серверов: Элементы сервера](../mfc/servers-server-items.md).

При создании серверного документа, платформа автоматически регистрирует документа в системе OLE библиотеки DLL. Это позволяет библиотеки DLL для определения сервера документов.

Дополнительные сведения см. в разделе [COleServerItem](../mfc/reference/coleserveritem-class.md) и [COleServerDoc](../mfc/reference/coleserverdoc-class.md) в *Справочник по библиотеке классов*.

## <a name="see-also"></a>См. также

[Серверы](../mfc/servers.md)<br/>
[серверы: Элементы сервера](../mfc/servers-server-items.md)<br/>
[серверы: Реализация сервера](../mfc/servers-implementing-a-server.md)<br/>
[серверы: Реализация Windows фрейма на месте](../mfc/servers-implementing-in-place-frame-windows.md)
