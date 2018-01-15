---
title: "Создание элемента управления списка | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 85afbe49943e06a66cf2fa914cc87f07b0fa8c52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-list-control"></a>Создание элемента управления "Список"
Как контролировать список ([CListCtrl](../mfc/reference/clistctrl-class.md)) создается зависит ли напрямую с помощью элемента управления или с помощью класса [CListView](../mfc/reference/clistview-class.md) вместо него. Если вы используете `CListView`, платформа создает представление как часть его последовательность создания документов и представлений. Создание представления списка создает список управления также (два — это то же самое). Элемент управления создается в представлении [OnCreate](../mfc/reference/cwnd-class.md#oncreate) функция-обработчик. В этом случае вы можете добавить элементы, используя вызов элемента управления [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl).  
  
### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>Использование CListCtrl непосредственно в диалоговом окне  
  
1.  В редакторе диалоговых окон Добавление элемента управления списка ваш ресурс шаблона диалоговых окон. Указать его идентификатор элемента управления.  
  
2.  Используйте [мастер добавления переменной члена](../ide/adding-a-member-variable-visual-cpp.md) для добавления переменной-члена типа `CListCtrl` со свойством элемента управления. Этот элемент можно использовать для вызова `CListCtrl` функции-члены.  
  
3.  Использование сопоставления функции обработчика в класс диалоговых окон для всех уведомлений, элемент управления списка сообщений в окне свойств необходимо обрабатывать (см. [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).  
  
4.  В [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), установка стилей для `CListCtrl`. В разделе [изменение стилей элемента управления списка](../mfc/changing-list-control-styles.md). Определяет тип «View», вы получаете в элементе управления, несмотря на то, что представление можно будет изменить позже.  
  
### <a name="to-use-clistctrl-in-a-nondialog-window"></a>Для использования в окне nondialog CListCtrl  
  
1.  Определение элемента управления в классе представления или окна.  
  
2.  Вызов элемента управления [создать](../mfc/reference/clistctrl-class.md#create) функция-член, возможно в [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), возможно уже в родительское окно [OnCreate](../mfc/reference/cwnd-class.md#oncreate) функция обработчика (Если вы являетесь Создание подкласса элемента управления). Установка стилей для элемента управления.  
  
## <a name="see-also"></a>См. также  
 [Использование CListCtrl](../mfc/using-clistctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

