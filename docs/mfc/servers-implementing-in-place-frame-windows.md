---
title: 'Серверы: Реализация фрейма на месте Windows | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], implementing
- OLE server applications [MFC], frame windows
- servers, in-place frame windows
- frame windows [MFC], in-place
- in-place frame windows
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6ef01a7943bbb0c14ec630651757a8665373b85
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055226"
---
# <a name="servers-implementing-in-place-frame-windows"></a>Серверы. Реализация окон фрейма на месте

В этой статье объясняется, что необходимо сделать для реализации окон фрейма на месте в приложении сервер визуального редактирования, если вы не используете мастер приложений для создания серверного приложения. Вместо выполнив процедуру, описанную в этой статье, можно использовать существующий класс окна фрейма на месте из мастера создания приложений приложения или пример, в состав Visual C++.

#### <a name="to-declare-an-in-place-frame-window-class"></a>Чтобы объявить класс окна фрейма на месте

1. Создать производный класс окна фрейма на месте из `COleIPFrameWnd`.

   - Используйте declare_dyncreate-макрос в файле заголовка класса.

   - Используйте implement_dyncreate-макрос в файле реализации (CPP) класса. Благодаря этому объекты этого класса, создаваемого платформой.

1. Объявите `COleResizeBar` член в класс окна фрейма. Это требуется, если требуется поддержка изменения размера на месте в серверных приложениях.

   Объявите `OnCreate` обработчик сообщений (с помощью **свойства** окна) и вызвать `Create` для вашей `COleResizeBar` члена, если она определена.

1. Если у вас есть панель инструментов, объявите `CToolBar` член в класс окна фрейма.

   Переопределить `OnCreateControlBars` функцию-член для создания панели инструментов, когда сервер активен на месте. Пример:

   [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]

   См. в обсуждении этого кода, выполнив шаг 5.

1. Включить файл заголовка для данного класса окна фрейма на месте в основной CPP-файле.

1. В `InitInstance` класса приложения, вызовите `SetServerInfo` функции объекта шаблона документа для указания ресурсов и окна фрейма на месте для использования в открытых, так и на месте редактирования.

Вызывает ряд функций в **Если** инструкция создает панели инструментов из ресурсов указанный сервер server. На этом этапе панели инструментов является частью контейнера окна иерархии. Поскольку эта панель инструментов является производным от `CToolBar`, его будет передавать его сообщения его владельцу окном фрейма приложения-контейнера, если не изменить владельца. Поэтому вызов `SetOwner` необходим. Этот вызов изменяет окно, где команды отправляются окон фрейма на месте сервера, вызывая сообщений, передаваемых на сервер. Это позволит серверу реагировать на операции на панели инструментов, который его предоставляет.

Идентификатор для точечного рисунка панели инструментов должен быть таким же, как другие ресурсы на месте, определенные в серверное приложение. См. в разделе [меню и ресурсы: Добавление серверов](../mfc/menus-and-resources-server-additions.md) подробные сведения.

Дополнительные сведения см. в разделе [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md), [COleResizeBar](../mfc/reference/coleresizebar-class.md), и [CDocTemplate::SetServerInfo](../mfc/reference/cdoctemplate-class.md#setserverinfo) в *Справочник по библиотеке классов*.

## <a name="see-also"></a>См. также

[Серверы](../mfc/servers.md)<br/>
[Серверы. Реализация сервера](../mfc/servers-implementing-a-server.md)<br/>
[Серверы. Реализация документов сервера](../mfc/servers-implementing-server-documents.md)<br/>
[Серверы. Элементы сервера](../mfc/servers-server-items.md)

