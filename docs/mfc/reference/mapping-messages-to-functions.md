---
title: Сопоставление сообщений с функциями | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.mapping.msg.function
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [MFC], adding message handlers
- message maps [MFC], mapping messages to functions
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 962a86139b7fdf8afac08e04e7b42240603b4374
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335530"
---
# <a name="mapping-messages-to-functions"></a>Сопоставление сообщений с функциями
Окно свойств позволяет привязать обработчики сообщений (функции-члены классов MFC пользовательского интерфейса) для сообщения, создаваемые ресурсы приложения. Они используют [схемы сообщений MFC](../../mfc/messages-and-commands-in-the-framework.md) для создания привязки.  
  
 При использовании представления классов, чтобы создать новый класс, производный от одного из классов framework, он автоматически помещается в полноценными и функциональными класса заголовка (.h) и реализации (CPP) файлов, указанных.  
  
> [!NOTE]
>  Чтобы добавить новый класс, который не обрабатывает сообщения, создайте класс, непосредственно в текстовом редакторе.  
  
### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>Определение или удаление обработчика сообщений в окне «Свойства»  
  
1.  Щелкните класс в представлении классов.  
  
2.  В окне «Свойства» щелкните **сообщений** кнопки.  
  
    > [!NOTE]
    >  **Сообщений** кнопка доступна при выборе имени класса в представлении классов или при нажатии кнопки в окне исходного кода.  
  
     Если проект имеет обработчик для сообщения, то имя обработчика отображается в правом столбце рядом с сообщением.  
  
3.  Если сообщение не имеет обработчика, затем щелкните ячейку в столбце справа от в окне «Свойства», чтобы отобразить предлагаемое имя обработчика в виде \<Добавить >*HandlerName*. (Например, обработчик сообщений WM_TIMER предложит \<Добавить >`OnTimer`).  
  
4.  Щелкните предлагаемое имя, чтобы добавить код заглушки для функции.  
  
5.  Чтобы изменить обработчик сообщений, дважды щелкните сообщение в представлении классов и редактировать код в окне исходного кода.  
  
 Чтобы удалить обработчик сообщений, дважды щелкните обработчик в правом столбце и выберите \<удалить >*HandlerName*. Код функции закомментируется.  
  
## <a name="see-also"></a>См. также  
 [Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../../ide/adding-a-class-visual-cpp.md)   
 [Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Добавление обработчиков событий для элементов управления диалогового окна](../../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)
