---
title: 'Контейнеры элементов ActiveX: Вставка элемента управления в приложение контейнера элемента управления | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f025c9fa564bcd37c585db6ea5c5cd0f5be83e0d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432144"
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>Контейнеры элементов управления ActiveX. Вставка элемента управления в приложение контейнера элемента управления

Прежде чем элемент управления ActiveX можно получить из приложения контейнера элемента управления ActiveX, необходимо добавить элемент управления ActiveX в контейнере приложений с помощью [Вставка элемента ActiveX](../windows/insert-activex-control-dialog-box.md) диалоговое окно.

Чтобы добавить элемент управления ActiveX в проект контейнера элемента управления ActiveX, см. в разделе [просмотра и добавление элементов управления ActiveX в диалоговое окно](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).

После добавления элемента управления, необходимо добавить переменную-член (ActiveX типа элемента управления) для класса диалогового окна. Дополнительные сведения об этой процедуре см. в разделе [Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md).

После добавления переменной-члена класса, называют класс-оболочку, автоматически создается и добавляется в проект. Этот класс используется в качестве интерфейса между контейнера элемента управления и внедренного элемента управления.

## <a name="see-also"></a>См. также

[Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)

