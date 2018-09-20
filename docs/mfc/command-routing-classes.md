---
title: Классы маршрутизации команд | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.command
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], classes
ms.assetid: 4b50e689-2c54-4e6c-90f0-37333e22b2a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b467a85aca4bb1d0405f9bbddee5cb5e4f5b790
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391553"
---
# <a name="command-routing-classes"></a>Классы маршрутизации команд

Как пользователь взаимодействует с приложением, выбрав меню или кнопки панели элементов управления с помощью мыши, приложение отправляет сообщения из объекта затронутых пользовательского интерфейса на соответствующий объект целевого объекта команды. Целевой объект команды классы, производные от `CCmdTarget` включают [CWinApp](../mfc/reference/cwinapp-class.md), [CWnd](../mfc/reference/cwnd-class.md), [CDocTemplate](../mfc/reference/cdoctemplate-class.md), [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), и классов, производных от них. Платформа поддерживает автоматическое команда маршрутизации таким образом, чтобы команды могут быть обработаны наиболее подходящий объект активной в приложении.

Объект класса `CCmdUI` передается команде целей команды обновления пользовательского интерфейса ([ON_UPDATE_COMMAND_UI](reference/message-map-macros-mfc.md#on_update_command_ui)) обработчики, чтобы можно было обновить состояние пользовательского интерфейса для определенной команды (например, необходимо проверить или удалить записи после изменения из пунктов меню). Вы вызов функций-членов из `CCmdUI` объекта, чтобы обновить состояние объекта пользовательского интерфейса. Этот процесс аналогичен является ли объект пользовательского интерфейса, связанный с конкретной команды пункта меню или кнопки или оба.

[CCmdTarget](../mfc/reference/ccmdtarget-class.md)<br/>
Служит базовым классом для всех классов, объектов, которые могут получать и обрабатывать сообщения.

[CCmdUI](../mfc/reference/ccmdui-class.md)<br/>
Предоставляет программный интерфейс для обновления объектов пользовательского интерфейса, таких как команды меню или кнопки панели элементов управления. Целевой объект команды включает, отключает, проверяет и очищает объект пользовательского интерфейса с данным объектом.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)

