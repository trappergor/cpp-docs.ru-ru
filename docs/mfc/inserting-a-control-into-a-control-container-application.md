---
title: Контейнеры элементов управления ActiveX. Вставка элемента управления в приложение контейнера элемента управления
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
ms.openlocfilehash: 1d2fc82628b3bcf842a6efb1d36ab9e8389fc0ba
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618499"
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>Контейнеры элементов управления ActiveX. Вставка элемента управления в приложение контейнера элемента управления

Прежде чем можно будет получить доступ к элементу управления ActiveX из приложения контейнера элементов управления ActiveX, необходимо добавить элемент управления ActiveX в приложение контейнера с помощью диалогового окна « [Вставка элемента управления ActiveX](../windows/insert-activex-control-dialog-box.md) ».

Сведения о добавлении элемента управления ActiveX в проект контейнера элемента управления ActiveX см. в разделе [Просмотр и добавление элементов управления ActiveX в диалоговое окно](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).

После добавления элемента управления необходимо добавить переменную-член (типа элемента управления ActiveX) в класс диалогового окна. Дополнительные сведения об этой процедуре см. в разделе [Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md).

После добавления переменной-члена класс, называемый классом-оболочкой, автоматически создается и добавляется в проект. Этот класс используется в качестве интерфейса между контейнером элемента управления и внедренным элементом управления.

## <a name="see-also"></a>См. также раздел

[Контейнеры элементов управления ActiveX](activex-control-containers.md)
