---
title: Контейнеры элементов управления ActiveX. Вставка элемента управления в приложение контейнера элемента управления
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
ms.openlocfilehash: e8426fd7a420ef06650930e547d06c78cc094975
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503098"
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>Контейнеры элементов управления ActiveX. Вставка элемента управления в приложение контейнера элемента управления

Прежде чем можно будет получить доступ к элементу управления ActiveX из приложения контейнера элементов управления ActiveX, необходимо добавить элемент управления ActiveX в приложение контейнера с помощью диалогового окна « [Вставка элемента управления ActiveX](../windows/adding-editing-or-deleting-controls.md) ».

Сведения о добавлении элемента управления ActiveX в проект контейнера элемента управления ActiveX см. в разделе [Просмотр и добавление элементов управления ActiveX в диалоговое окно](../windows/adding-editing-or-deleting-controls.md).

После добавления элемента управления необходимо добавить переменную-член (типа элемента управления ActiveX) в класс диалогового окна. Дополнительные сведения об этой процедуре см. в разделе [Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md).

После добавления переменной-члена класс, называемый классом-оболочкой, автоматически создается и добавляется в проект. Этот класс используется в качестве интерфейса между контейнером элемента управления и внедренным элементом управления.

## <a name="see-also"></a>См. также раздел

[Контейнеры элементов управления ActiveX](activex-control-containers.md)
