---
title: Обеспечение взаимодействия с мышью в неактивном режиме
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], mouse interaction
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
ms.openlocfilehash: d37deeec06551ae8bf340c99a9759327ce2ec2b7
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287847"
---
# <a name="providing-mouse-interaction-while-inactive"></a>Обеспечение взаимодействия с мышью в неактивном режиме

Если элемент управления не будет активирован сразу же, все равно имеет смысл сделать этот процесс WM_SETCURSOR и wm_mousemove и сообщения, несмотря на то, что элемент управления не имеет окна свои собственные. Это можно сделать, включив `COleControl`в реализации `IPointerInactive` интерфейс, который по умолчанию отключена. (См. в разделе *ActiveX SDK* описание этого интерфейса.) Чтобы включить ее, включать флаг pointerInactive в набор флагов, возвращенный [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags):

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_3.cpp)]

Код, включив этот флаг создается автоматически при выборе **мыши указатель уведомления при неактивной** параметр [параметры управления](../mfc/reference/control-settings-mfc-activex-control-wizard.md) странице при создании элемента управления с помощью **Мастер элементов ActiveX MFC**.

Когда `IPointerInactive` интерфейс включен, контейнер делегирует WM_SETCURSOR и wm_mousemove и сообщений, к нему. `COleControl`в реализации `IPointerInactive` отправляет сообщения через схему сообщений элемента управления, после настройки мыши координирует соответствующим образом. Можно обработать сообщения, так же, как обычные окна сообщения, добавив соответствующие записи в схеме сообщений. В вашей обработчики для этих сообщений, избегайте использования *m_hWnd* переменную-член (или любой использующей ее функция-член), что его значение не равно **NULL**.

Вы также можете неактивный элемент управления, чтобы быть целевым объектом операции перетаскивания и вставки OLE. Для этого требуется активация элемент управления в момент, когда пользователь перетаскивает объект, таким образом, чтобы окна элемента управления могут быть зарегистрированы в качестве цели перетаскивания. Чтобы вызвать активации при перетаскивания, переопределите [COleControl::GetActivationPolicy](../mfc/reference/colecontrol-class.md#getactivationpolicy)и возвращает флаг POINTERINACTIVE_ACTIVATEONDRAG:

[!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_4.cpp)]

Включение `IPointerInactive` интерфейс обычно означает, что элемент управления, чтобы иметь возможность обработать сообщения мыши все время. Для этого в контейнере, который не поддерживает `IPointerInactive` интерфейс, необходимо иметь элемент управления всегда активировано при отображении, то есть элемент управления должен включать флаг OLEMISC_ACTIVATEWHENVISIBLE среди прочих флаги. Тем не менее, чтобы предотвратить этот флаг из вступают в силу в контейнере, поддерживает ли `IPointerInactive`, можно также указать флаг OLEMISC_IGNOREACTIVATEWHENVISIBLE:

[!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_5.cpp)]

## <a name="see-also"></a>См. также

[Элементы ActiveX в MFC. Оптимизация](../mfc/mfc-activex-controls-optimization.md)
