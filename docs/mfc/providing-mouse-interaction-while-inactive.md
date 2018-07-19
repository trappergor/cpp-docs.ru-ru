---
title: Обеспечение взаимодействия с мышью неактивном режиме | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], mouse interaction
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c322493a0ee1aebd068ffe1fedb695445b6274aa
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929498"
---
# <a name="providing-mouse-interaction-while-inactive"></a>Обеспечение взаимодействия с мышью в неактивном режиме
Если элемент управления не будет активирован немедленно, по-прежнему можно их в процессе WM_SETCURSOR и WM_MOUSEMOVE сообщения, даже если элемент управления не имеет окна свои собственные. Это можно сделать, включив `COleControl`реализация `IPointerInactive` интерфейс, который по умолчанию отключена. (См. *ActiveX SDK* описание этого интерфейса.) Чтобы включить его, включить флаг pointerInactive в набор флагов, возвращенных [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags):  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_3.cpp)]  
  
 Код, чтобы включить этот флаг создается автоматически при выборе **мыши указатель уведомления при неактивные** параметр [параметры управления](../mfc/reference/control-settings-mfc-activex-control-wizard.md) страницы при создании элемента управления с **Мастер элементов управления ActiveX MFC**.  
  
 Когда `IPointerInactive` интерфейс включен, контейнер делегирует WM_SETCURSOR и WM_MOUSEMOVE сообщения к нему. `COleControl`в реализации `IPointerInactive` отправляет сообщения через схему сообщений для элемента управления, после настройки мыши координирует соответствующим образом. Можно обработать сообщения так же, как обычные окна сообщения, добавив соответствующие записи в схеме сообщений. В вашей обработчики для этих сообщений, избегайте использования *m_hWnd* переменную-член (или любую функцию-член, которые его используют) без проверки, его значение не **NULL**.  
  
 Вы также можете неактивный элемент управления, чтобы быть целевым объектом операции перетаскивания и вставки OLE. Это требует активации элемента управления в момент, когда пользователь перетаскивает объект, так что окна элемента управления могут быть зарегистрированы в качестве цели перетаскивания. Чтобы во время перетаскивания успешной активации, переопределите [COleControl::GetActivationPolicy](../mfc/reference/colecontrol-class.md#getactivationpolicy)и возвращают флаг POINTERINACTIVE_ACTIVATEONDRAG:  
  
 [!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_4.cpp)]  
  
 Включение `IPointerInactive` интерфейс обычно означает, что требуется, чтобы элемент управления, чтобы обеспечить возможность обработки сообщений мыши все время. Для получения этого поведения в контейнере, который не поддерживает `IPointerInactive` интерфейса, необходимо иметь элемент управления всегда активировано при отображении, то есть элемент управления должен включать флаг OLEMISC_ACTIVATEWHENVISIBLE среди прочих флаги. Однако во избежание этого флага из вступают в силу в контейнере, который поддерживает `IPointerInactive`, можно также указать флаг OLEMISC_IGNOREACTIVATEWHENVISIBLE:  
  
 [!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_5.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX в MFC. Оптимизация](../mfc/mfc-activex-controls-optimization.md)

