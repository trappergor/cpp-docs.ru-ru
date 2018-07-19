---
title: Типы, связанные с объектами пользовательского интерфейса сообщений | Документация Майкрософт
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
ms.openlocfilehash: b7ecc948910dd618f343134b0e9e3133539d9e1f
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335484"
---
# <a name="message-types-associated-with-user-interface-objects"></a>Типы сообщений, связанных с объектами пользовательского интерфейса
Ниже приведены типы объектов, с которыми работают и типы сообщений, связанных с ними.  
  
### <a name="user-interface-objects-and-associated-messages"></a>Объекты пользовательского интерфейса и связанные сообщения  
  
|Идентификатор объекта|Сообщения|  
|---------------|--------------|  
|Класс, представляющий имя содержащего его окна|Сообщения Windows, допустимые для [CWnd](../../mfc/reference/cwnd-class.md)-производный класс: диалоговое окно, окно, дочернее окно, дочернее окно MDI или верхний фрейм окна.|  
|Идентификатор меню или сочетание клавиш|-Сообщение КОМАНДЫ (выполнение функции программы).<br />-Сообщение UPDATE_COMMAND_UI (динамически обновляет элемент меню).|  
|Идентификатор элемента управления|Уведомляющих сообщений элемента управления типа выбранного элемента управления.|  
  
## <a name="see-also"></a>См. также  
 [Сопоставление сообщений с функциями](../../mfc/reference/mapping-messages-to-functions.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../../ide/adding-a-class-visual-cpp.md)   
 [Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)
