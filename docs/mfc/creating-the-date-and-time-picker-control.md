---
title: Создание элемента выбора времени и даты | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ce7c987bf1284d0287cd0206572209d7ae2d0b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="creating-the-date-and-time-picker-control"></a>Создание элемента выбора даты и времени
Способ создания элемента управления выбора даты и времени зависит от того, с помощью элемента управления в диалоговом окне или его создания в окне nondialog.  
  
### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>Использование CDateTimeCtrl непосредственно в диалоговом окне  
  
1.  В редакторе диалоговых окон добавьте дату и время управления выбора для вашего ресурса шаблона диалогового окна. Указать его идентификатор элемента управления.  
  
2.  Укажите любые стили обязательно, используя диалоговое окно свойств элемента управления выбора даты и времени.  
  
3.  Используйте [мастер добавления переменной члена](../ide/adding-a-member-variable-visual-cpp.md) для добавления переменной-члена типа [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) со свойством элемента управления. Этот элемент можно использовать для вызова `CDateTimeCtrl` функции-члены.  
  
4.  Используйте окно свойств для сопоставления функции обработчика в класс диалоговых окон для любого элементе управления [уведомления](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) необходимо обрабатывать сообщения (в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).  
  
5.  В [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), задайте любые дополнительные стили для `CDateTimeCtrl` объекта.  
  
### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>Для использования в окне nondialog CDateTimeCtrl  
  
1.  Объявите элемент управления в классе представления или окна.  
  
2.  Вызов элемента управления [создать](../mfc/reference/ctabctrl-class.md#create) функция-член, возможно в [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), возможно уже в родительское окно [OnCreate](../mfc/reference/cwnd-class.md#oncreate) функция обработчика (Если вы являетесь Создание подкласса элемента управления). Установка стилей для элемента управления.  
  
## <a name="see-also"></a>См. также  
 [Использование CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

