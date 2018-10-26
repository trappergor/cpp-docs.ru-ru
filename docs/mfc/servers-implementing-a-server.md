---
title: 'Серверы: Реализация сервера | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- servers, implementing
- OLE server applications [MFC], implementing OLE servers
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1dd43b806852e578c28dc7a647cb367ad6f2780
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076624"
---
# <a name="servers-implementing-a-server"></a>Серверы. Реализация сервера

В этой статье объясняется, мастер приложений MFC создает для визуального редактирования серверного приложения. Если вы не используете мастер приложений, в этой статье перечислены области, где необходимо написать код для реализации серверного приложения.

Если вы используете мастер приложений для создания нового серверного приложения, он предоставляет значительное количество кода конкретного сервера. При добавлении визуального редактирования функции сервера в существующее приложение, необходимо дублировать код в мастере приложений будет предоставленные перед добавлением остальные необходимые серверный код.

Серверный код, предлагаемое мастером приложений подразделяется на несколько категорий.

- Определение ресурсов сервера:

   - Меню ресурса, используемого при сервер редактируется внедренного элемента в отдельном окне.

   - Меню и панели инструментов ресурсов, используемых при сервер активен на месте.

   Дополнительные сведения об этих ресурсах см. в разделе [меню и ресурсы: Добавление серверов](../mfc/menus-and-resources-server-additions.md).

- Определив элемент класс производным от `COleServerItem`. Дополнительные сведения для элементов сервера см. в разделе [серверов: элементы сервера](../mfc/servers-server-items.md).

- Изменение базового класса для класса документа `COleServerDoc`. Дополнительные сведения см. в разделе [серверы: реализация документов сервера](../mfc/servers-implementing-server-documents.md).

- Определение класса окна фрейма производным от `COleIPFrameWnd`. Дополнительные сведения см. в разделе [серверы: реализация Windows фрейма на месте](../mfc/servers-implementing-in-place-frame-windows.md).

- Создание записи для серверного приложения в базе данных регистрации Windows и регистрации нового экземпляра сервера в системе OLE. Сведения по этой теме см. в разделе [регистрации](../mfc/registration.md).

- Инициализация и запуск приложения сервера. Сведения по этой теме см. в разделе [регистрации](../mfc/registration.md).

Дополнительные сведения см. в разделе [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerDoc](../mfc/reference/coleserverdoc-class.md), и [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md) в *Справочник по библиотеке классов*.

## <a name="see-also"></a>См. также

[Серверы](../mfc/servers.md)<br/>
[Контейнеры](../mfc/containers.md)<br/>
[Меню и ресурсы (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Регистрация](../mfc/registration.md)

