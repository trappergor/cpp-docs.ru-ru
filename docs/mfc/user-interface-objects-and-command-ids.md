---
title: Объекты пользовательского интерфейса и идентификаторы команд | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts, associating with IDs
- MFC, command routing
- toolbar controls [MFC], command ID
- menu items, associating with IDs
- user interface objects [MFC], associating with IDs
- command IDs, user interface objects
- command routing [MFC], MFC
- command handling [MFC], user-interface objects
ms.assetid: 4ea19e9b-ed1e-452e-bd33-7f509107a45b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b56babf0e42dde521a6bda3a7d9713db519182c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385603"
---
# <a name="user-interface-objects-and-command-ids"></a>Объекты пользовательского интерфейса и идентификаторы команд
Пункты меню, кнопки панели инструментов и сочетания клавиш являются «объектов пользовательского интерфейса» может создавать команды. Каждый такой объект пользовательского интерфейса имеет идентификатор. Связать объект пользовательского интерфейса с помощью команды, назначив тот же идентификатор объекта и команды. Как описано в статье [сообщения](../mfc/messages.md), реализуются как специальные сообщения. На рисунке «Команд в Framework» ниже показано, как среда управляет команд. Когда объект пользовательского интерфейса создает команду, такие как `ID_EDIT_CLEAR_ALL`, один из объектов в приложении обрабатывает команды — на рисунке ниже, объект документа `OnEditClearAll` функция вызывается с помощью схемы сообщений для документа.  
  
 ![Команды в Framework](../mfc/media/vc385p1.gif "vc385p1")  
Команды в Framework  
  
 На рисунке «Команда обновления в Framework» ниже показано, как обновления MFC для объектов пользовательского интерфейса, например, пункты меню и кнопки панели инструментов. Прежде чем раскрывающееся меню или во время цикла простоя в случае кнопки панели инструментов, MFC направляет команды update. На рисунке ниже, объект документа вызывает обработчик команды обновлений, `OnUpdateEditClearAll`, чтобы включить или отключить объект пользовательского интерфейса.  
  
 ![Команда обновления в структуре](../mfc/media/vc385p2.png "vc385p2")  
Обновление команд в Framework  
  
## <a name="see-also"></a>См. также  
 [Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

