---
title: Классы маршрутизации команд | Документы Microsoft
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
ms.openlocfilehash: f3e05046ac6754dd585bb1fbf51420ef862af7be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341966"
---
# <a name="command-routing-classes"></a>Классы маршрутизации команд
Как пользователь взаимодействует с приложением, выбрав меню или кнопок панели элементов управления с помощью мыши, приложение отправляет сообщения из объекта затронутых пользовательского интерфейса соответствующий целевой объект команды. Целевой объект команды классы, производные от `CCmdTarget` включают [CWinApp](../mfc/reference/cwinapp-class.md), [CWnd](../mfc/reference/cwnd-class.md), [CDocTemplate](../mfc/reference/cdoctemplate-class.md), [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), и классов, производных от них. Платформа поддерживает автоматическое команда маршрутизации, команды могут обрабатываться самый подходящий объект активного в приложении.  
  
 Объект класса `CCmdUI` передается команды update целей команды пользовательского интерфейса ([ON_UPDATE_COMMAND_UI](reference/message-map-macros-mfc.md#on_update_command_ui)) обработчики, чтобы можно было обновить состояние пользовательского интерфейса для конкретной команды (например, необходимо проверить или remove Проверка из пунктов меню). Вызова функции-члена `CCmdUI` объекта, чтобы обновить состояние объекта пользовательского интерфейса. Этот процесс одинаков является ли объект пользовательского интерфейса, связанные с определенной команды пункта меню или кнопки или оба.  
  
 [CCmdTarget](../mfc/reference/ccmdtarget-class.md)  
 Служит базовым классом для всех классов объектов, которые могут получать и реагировать на сообщения.  
  
 [CCmdUI](../mfc/reference/ccmdui-class.md)  
 Обеспечивает программный интерфейс для обновления объектов пользовательского интерфейса, такие как элементы меню или кнопок панели управления. Целевой объект команды включает, отключает, проверяет и очищает объект пользовательского интерфейса с этим объектом.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

