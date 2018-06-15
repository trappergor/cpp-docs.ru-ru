---
title: Добавление обработчика событий (Visual C++) | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.eventhandler.overview
dev_langs:
- C++
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 184161b22358f77845b5f7c4b6da0bb42f3ea15f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324919"
---
# <a name="adding-an-event-handler-visual-c"></a>Добавление обработчика событий (Visual C++)
В редакторе ресурсов можно добавить новый обработчик событий или изменить существующий для элемента управления диалогового окна с помощью [мастера обработчика события](../ide/event-handler-wizard.md).  
  
 Вы можете добавить событие в класс, реализующий диалоговое окно, с помощью [окна свойств](/visualstudio/ide/reference/properties-window). Если вы хотите добавить событие в класс, отличный от класса диалогового окна, используйте мастер обработчика события.  
  
### <a name="to-add-an-event-handler-to-a-dialog-box-control"></a>Добавление обработчика событий для элемента управления диалогового окна  
  
1.  Дважды щелкните ресурс диалогового окна в [представлении ресурсов](../windows/resource-view-window.md), чтобы открыть ресурс диалогового окна, содержащий нужный элемент управления, в [редакторе диалоговых окон](../windows/dialog-editor.md).  
  
2.  Щелкните правой кнопкой мыши элемент управления, для которого нужно обработать событие уведомления.  
  
3.  В контекстном меню щелкните **Добавить обработчик события**, чтобы открыть мастер обработчика события.  
  
4.  Выберите событие в поле **Тип сообщений**, чтобы добавить в класс, выбранный в поле **Список классов**.  
  
5.  Примите имя по умолчанию в поле **Имя функции-обработчика** или введите другое имя.  
  
6.  Щелкните **Добавить и изменить**, чтобы добавить обработчик событий в проект и открыть текстовый редактор с новой функцией для добавления необходимого кода обработчика событий.  
  
     Если выбранный тип сообщений уже имеет обработчик событий для выбранного класса, элемент **Добавить и изменить** недоступен, а доступен элемент **Редактировать код**. Щелкните **Редактировать код**, чтобы открыть текстовый редактор с существующей функцией.  
  
 Кроме того, можно добавить обработчики событий из [окна свойств](/visualstudio/ide/reference/properties-window). Дополнительные сведения см. в разделе [Добавление обработчиков событий для элементов управления диалоговых окон](../windows/adding-event-handlers-for-dialog-box-controls.md).  
  
## <a name="see-also"></a>См. также  
 [Добавление функциональных возможностей с помощью мастеров кода](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../ide/adding-a-class-visual-cpp.md)   
 [Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md)   
 [Добавление функции-члена](../ide/adding-a-member-function-visual-cpp.md)   
 [Обработчик сообщений MFC](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Перемещение по структуре класса](../ide/navigating-the-class-structure-visual-cpp.md)