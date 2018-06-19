---
title: Типы, связанные с объектами пользовательского интерфейса сообщений | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.uiobject.msgs
dev_langs:
- C++
helpviewer_keywords:
- message types and user interface objects [MFC]
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14a2309556ca6c5204247ccbe916aebe472a1da1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373428"
---
# <a name="message-types-associated-with-user-interface-objects"></a>Типы сообщений, связанных с объектами пользовательского интерфейса
Ниже приведены типы объектов, с которыми можно работать и типы сообщений, связанных с ними.  
  
### <a name="user-interface-objects-and-associated-messages"></a>Объекты пользовательского интерфейса и связанных сообщений  
  
|Идентификатор объекта|Сообщения|  
|---------------|--------------|  
|Имя класса, представляющее содержащее окно|Сообщения Windows, допустимые для [CWnd](../../mfc/reference/cwnd-class.md)-производного класса: диалоговое окно, окно, дочернее окно, дочернее окно MDI или верхний фрейм окна.|  
|Идентификатор меню или сочетаний клавиш|-   **КОМАНДА** сообщение (выполнение функции программы).<br />-   **UPDATE_COMMAND_UI** сообщение (динамически обновляет элемент меню).|  
|Идентификатор элемента управления|Уведомляющих сообщений элемента управления для выбранного типа элемента управления.|  
  
## <a name="see-also"></a>См. также  
 [Сопоставление сообщений с функциями](../../mfc/reference/mapping-messages-to-functions.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../../ide/adding-a-class-visual-cpp.md)   
 [Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)
