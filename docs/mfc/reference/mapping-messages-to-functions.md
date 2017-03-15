---
title: "Сопоставление сообщений с функциями | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.mapping.msg.function
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [C++], adding message handlers
- message maps [C++], mapping messages to functions
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 584cc8b1f59f94d88718add5c21046c487b8556f
ms.lasthandoff: 02/24/2017

---
# <a name="mapping-messages-to-functions"></a>Сопоставление сообщений с функциями
Окно свойств позволяет привязать обработчики сообщений (функции-члены классов пользовательского интерфейса MFC) сообщения, созданные ресурсы приложения. Они используют [схемы сообщений MFC](../../mfc/messages-and-commands-in-the-framework.md) для создания привязки.  
  
 При использовании представления классов для создания нового класса, производного от одного из классов framework, он автоматически помещается в полные и рабочие класс заголовков (h) и реализации (CPP) файлы, указанные.  
  
> [!NOTE]
>  Чтобы добавить новый класс, не выполняющий обработку сообщений, создайте класс непосредственно в текстовом редакторе.  
  
### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>Определение или удаление обработчика сообщений в окне «Свойства»  
  
1.  В представлении классов щелкните класс.  
  
2.  В окне свойств щелкните **сообщений** кнопки.  
  
    > [!NOTE]
    >  **Сообщений** кнопка доступна при выборе имени класса в представлении классов или при нажатии кнопки в окне исходного кода.  
  
     Если проект содержит обработчик для сообщения, имя обработчика появляется в правом столбце рядом с сообщением.  
  
3.  Если сообщение не имеет обработчика, затем щелкните ячейку в правом столбце в окне «Свойства», чтобы отобразить предлагаемое имя обработчика как \<добавьте настроек*HandlerName*. (Например, `WM_TIMER` обработчик сообщений предлагает \<добавьте настроек`OnTimer`).  
  
4.  Щелкните предлагаемое имя, чтобы добавить код-заглушку для функции.  
  
5.  Чтобы изменить обработчик сообщения, дважды щелкните сообщение в окне классов и измените код в окне исходного кода.  
  
 Чтобы удалить обработчик сообщения, дважды щелкните обработчик в правом столбце и выберите \<Удаление настроек*HandlerName*. Код функции будет закомментирован.  
  
## <a name="see-also"></a>См. также  
 [Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../../ide/adding-a-class-visual-cpp.md)   
 [Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Добавление обработчиков событий для элементов управления диалогового окна](../../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)

