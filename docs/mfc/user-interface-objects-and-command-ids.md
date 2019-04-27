---
title: Объекты пользовательского интерфейса и идентификаторы команд
ms.date: 11/19/2018
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
ms.openlocfilehash: 54372facc51062add122c1db2e01e3081127512e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180626"
---
# <a name="user-interface-objects-and-command-ids"></a>Объекты пользовательского интерфейса и идентификаторы команд

Элементы меню, кнопки панели инструментов и сочетания клавиш являются «объекты пользовательского интерфейса» для создания команды. Каждый такой объект пользовательского интерфейса имеет идентификатор. Связать объект пользовательского интерфейса с помощью команды путем назначения и тот же идентификатор объекта и команды. Как описано в [сообщений](../mfc/messages.md), команды, реализуются в виде специальных сообщений. На рисунке «Команд в Framework» ниже показано, как среда управляет команды. Когда объект пользовательского интерфейса генерирует команды, такие как `ID_EDIT_CLEAR_ALL`, один из объектов в приложении обрабатывает команду, на рисунке ниже, объект документа `OnEditClearAll` функция вызывается через схему сообщений для документа.

![Команды платформы](../mfc/media/vc385p1.gif "команды платформы") <br/>
Команды в Framework

На рисунке «Команда обновления в Framework» ниже показано, как MFC обновляет объекты пользовательского интерфейса, такие как элементы меню и кнопки панели инструментов. Прежде чем раскрывающимся меню, или во время цикла простоя в случае кнопки панели инструментов, MFC направляет команды update. На рисунке ниже, объект документа, вызывает обработчик команды обновлений, `OnUpdateEditClearAll`, чтобы включить или отключить объект пользовательского интерфейса.

![Команда обновления в структуре](../mfc/media/vc385p2.png "команды обновления в Framework") <br/>
Обновление команд в Framework

## <a name="see-also"></a>См. также

[Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)
