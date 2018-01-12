---
title: "Элементов управления MFC ActiveX: События | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- notifications [MFC], notifying containers of events
- custom events [MFC], adding to ActiveX controls
- events [MFC], mapping
- COleControl class [MFC], handling of events
- mappings [MFC], events
- stock events [MFC]
- container events [MFC]
- events [MFC], ActiveX controls
- OLE events [MFC]
ms.assetid: e1e57e0c-206b-4923-a0b5-682c26564f74
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b6760f2051542a28e78f5f8f2fa81f6937388d82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-events"></a>Элементы управления ActiveX в MFC. События
Элементы управления ActiveX использовать события для уведомления о том, что-то произошло в элемент управления контейнера. Распространенные примеры событий включают щелчков мыши на элементе управления, данные, введенные с помощью клавиатуры и изменения в состоянии элемента управления. При возникновении этих действий, элемент управления инициирует событие для создания предупреждения контейнера.  
  
 События также называются сообщения.  
  
 MFC поддерживает два типа событий: стандартных и пользовательских. Стандартных событий являются те события, которые класс [COleControl](../mfc/reference/colecontrol-class.md) обрабатывает автоматически. Полный список стандартных событий см. в статье [элементы управления MFC ActiveX: Добавление события Stock](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md). Пользовательские события позволяют элемент управления может уведомлять выполнения действия, относящиеся к данному элементу контейнера. Некоторые примеры бы изменения внутреннего состояния элемента управления или получение определенных окна сообщения.  
  
 Элемент управления для порождения событий должным образом класса элемента управления необходимо сопоставить каждое событие элемента управления на функцию-член, который должен вызываться при возникновении соответствующего события. Этот механизм сопоставления (называется картой событий) содержит централизованные сведения о событии и позволяет среде Visual Studio легко доступ и использовать события элемента управления. На этой карте событие объявляется с следующий макрос, расположенный в заголовке (. H) файла объявления класса элемента управления.  
  
 [!code-cpp[NVC_MFC_AxUI#2](../mfc/codesnippet/cpp/mfc-activex-controls-events_1.h)]  
  
 После объявления события карты, он должен быть определен в реализации элемента управления (. Файл CPP). Следующие строки кода определяют схема событий, что элемент управления для запуска определенных событий:  
  
 [!code-cpp[NVC_MFC_AxUI#3](../mfc/codesnippet/cpp/mfc-activex-controls-events_2.cpp)]  
[!code-cpp[NVC_MFC_AxUI#4](../mfc/codesnippet/cpp/mfc-activex-controls-events_3.cpp)]  
  
 При использовании мастера элементов управления ActiveX MFC для создания проекта автоматически добавит эти строки. Если не выполнить мастер элементов управления ActiveX MFC, необходимо добавить эти строки вручную.  
  
 Представление классов, можно добавить поддерживается классом событий хранения `COleControl` или пользовательских событий, которые указываются. Для каждого нового события представления классов автоматически добавляет соответствующие записи карты события элемента управления и элемента управления. IDL-файл.  
  
 Два других статьях рассматриваются события подробно:  
  
-   [Элементы управления ActiveX MFC: Добавление событий хранения](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [Элементы ActiveX в MFC. Добавление пользовательских событий](../mfc/mfc-activex-controls-adding-custom-events.md)  
  
## <a name="see-also"></a>См. также  
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Элементы управления MFC ActiveX: методы](../mfc/mfc-activex-controls-methods.md)   
 [Класс COleControl](../mfc/reference/colecontrol-class.md)
