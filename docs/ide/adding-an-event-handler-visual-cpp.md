---
title: "Добавление обработчика событий (Visual C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.eventhandler.overview
dev_langs:
- C++
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9a5380bf335a13bbf7b2f54840c9d1160187167
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-event-handler-visual-c"></a>Добавление обработчика событий (Visual C++)
В редакторе ресурсов можно добавить новый обработчик событий, или изменить существующий обработчик событий для диалогового окна элемента управления при помощи [мастер обработчиков событий](../ide/event-handler-wizard.md).  
  
 События можно добавить к классу, реализующему диалогового окна с помощью [окно свойств](/visualstudio/ide/reference/properties-window). Если вы хотите добавить событие класса, отличного от класса диалогового окна, используйте мастер обработчиков событий.  
  
### <a name="to-add-an-event-handler-to-a-dialog-box-control"></a>Чтобы добавить обработчик событий для управления диалогового окна  
  
1.  Дважды щелкните ресурс диалогового окна в [представление ресурсов](../windows/resource-view-window.md) открыть ресурс диалогового окна, содержащего элемент управления в [редактор диалоговых окон](../windows/dialog-editor.md).  
  
2.  Щелкните правой кнопкой мыши элемент управления, для которого необходимо обработать событие уведомления.  
  
3.  В контекстном меню щелкните **добавить обработчик событий** чтобы открыть мастер обработчиков событий.  
  
4.  Выберите событие в **тип сообщений** позволяет добавить в класс, выбранный в **список классов** поле.  
  
5.  Примите имя по умолчанию в **имя функции обработчика** поле или введите другое имя по своему усмотрению.  
  
6.  Нажмите кнопку **добавить и изменить** для добавления обработчика событий в проект и откройте текстовый редактор на новой функции, чтобы добавить необходимый код обработки событий.  
  
     Если тип выбранного сообщения уже имеет обработчик событий для выбранного класса **добавить и изменить** недоступны, и **редактирования кода** доступен. Нажмите кнопку **редактирования кода** чтобы открыть текстовый редактор на существующей функции.  
  
 Кроме того, можно добавить обработчики событий из [окно свойств](/visualstudio/ide/reference/properties-window). В разделе [Добавление обработчиков событий для элементов управления диалоговых](../windows/adding-event-handlers-for-dialog-box-controls.md) для получения дополнительной информации.  
  
## <a name="see-also"></a>См. также  
 [Добавление функциональных возможностей с помощью мастеров кода](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../ide/adding-a-class-visual-cpp.md)   
 [Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md)   
 [Добавление функции-члена](../ide/adding-a-member-function-visual-cpp.md)   
 [Обработчик сообщений MFC](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Перемещение по структуре класса](../ide/navigating-the-class-structure-visual-cpp.md)