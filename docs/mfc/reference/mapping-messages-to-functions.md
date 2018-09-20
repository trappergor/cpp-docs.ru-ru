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
ms.openlocfilehash: bb37637cbfc2ec0af96ed339da6e71cf349797e2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402880"
---
# <a name="mapping-messages-to-functions"></a>Сопоставление сообщений с функциями

Окно свойств позволяет привязать обработчики сообщений (функции-члены классов MFC пользовательского интерфейса) для сообщения, создаваемые ресурсы приложения. Они используют [схемы сообщений MFC](../../mfc/messages-and-commands-in-the-framework.md) для создания привязки.

При использовании представления классов, чтобы создать новый класс, производный от одного из классов framework, он автоматически помещается в полноценными и функциональными класса заголовка (.h) и реализации (CPP) файлов, указанных.

> [!NOTE]
>  Чтобы добавить новый класс, который не обрабатывает сообщения, создайте класс, непосредственно в текстовом редакторе.

### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>Определение или удаление обработчика сообщений в окне «Свойства»

1. Щелкните класс в представлении классов.

1. В окне «Свойства» щелкните **сообщений** кнопки.

    > [!NOTE]
    >  **Сообщений** кнопка доступна при выборе имени класса в представлении классов или при нажатии кнопки в окне исходного кода.

     Если проект имеет обработчик для сообщения, то имя обработчика отображается в правом столбце рядом с сообщением.

1. Если сообщение не имеет обработчика, затем щелкните ячейку в столбце справа от в окне «Свойства», чтобы отобразить предлагаемое имя обработчика в виде \<Добавить >*HandlerName*. (Например, обработчик сообщений WM_TIMER предложит \<Добавить >`OnTimer`).

1. Щелкните предлагаемое имя, чтобы добавить код заглушки для функции.

1. Чтобы изменить обработчик сообщений, дважды щелкните сообщение в представлении классов и редактировать код в окне исходного кода.

Чтобы удалить обработчик сообщений, дважды щелкните обработчик в правом столбце и выберите \<удалить >*HandlerName*. Код функции закомментируется.

## <a name="see-also"></a>См. также

[Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Добавление класса](../../ide/adding-a-class-visual-cpp.md)<br/>
[Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[Добавление обработчиков событий для элементов управления диалоговых окон](../../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)
