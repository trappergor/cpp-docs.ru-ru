---
title: Создание календарь на месяц управления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e5cb58cfbecd03964963814081c2f0039c0752c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="creating-the-month-calendar-control"></a>Создание элемента управления "Календарь на месяц"
Как создается управляющий элемент календаря зависит от того, с помощью элемента управления в диалоговом окне или его создания в окне nondialog.  
  
### <a name="to-use-cmonthcalctrl-directly-in-a-dialog-box"></a>Использование CMonthCalCtrl непосредственно в диалоговом окне  
  
1.  В редакторе диалоговых окон Добавление элемента управления календаря на месяц ваш ресурс шаблона диалоговых окон. Указать его идентификатор элемента управления.  
  
2.  Укажите любые стили, требуемое диалоговое окно свойств элемента управления calendar month.  
  
3.  Используйте [мастер добавления переменной члена](../ide/adding-a-member-variable-visual-cpp.md) для добавления переменной-члена типа [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md) со свойством элемента управления. Этот элемент можно использовать для вызова `CMonthCalCtrl` функции-члены.  
  
4.  Использование сопоставления функции обработчика в класс диалоговых окон сообщений уведомлений управления Календарь месяца, можно в окне свойств необходимо обрабатывать (см. [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).  
  
5.  В [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), задайте любые дополнительные стили для `CMonthCalCtrl` объекта.  
  
### <a name="to-use-cmonthcalctrl-in-a-nondialog-window"></a>Для использования в окне nondialog CMonthCalCtrl  
  
1.  Определение элемента управления в классе представления или окна.  
  
2.  Вызов элемента управления [создать](../mfc/reference/cmonthcalctrl-class.md#create) функция-член, возможно в [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), возможно уже в родительское окно [OnCreate](../mfc/reference/cwnd-class.md#oncreate) функция обработчика (Если вы являетесь Создание подкласса элемента управления). Установка стилей для элемента управления.  
  
## <a name="see-also"></a>См. также  
 [Использование CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

