---
title: "Создание элемента выбора времени и даты | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e9c0b99f42bef162ed3c571e19630f9227a8504e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

