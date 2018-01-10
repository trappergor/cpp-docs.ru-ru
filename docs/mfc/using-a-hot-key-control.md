---
title: "С помощью сочетания ключа элемента управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0a64de06d5bc499d5b566d6d40508d08e920264
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-hot-key-control"></a>Использование элемента управления "Сочетание клавиш"
Типичное использование горячей ключа управления соответствует шаблону ниже:  
  
-   Элемент управления создается. Если элемент управления, заданный в шаблон диалогового окна, создание выполняется автоматически при создании диалоговым окном. (Вы должны иметь [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) члена в классе диалогового окна, который соответствует горячей ключа управления.) Кроме того, можно использовать [создать](../mfc/reference/chotkeyctrl-class.md#create) функции-члена для создания элемента управления как дочернего окна любого окна.  
  
-   Если вы хотите установить значение по умолчанию для элемента управления, вызовите [SetHotKey](../mfc/reference/chotkeyctrl-class.md#sethotkey) функции-члена. Если вы хотите запретить определенных состояний shift, вызовите [SetRules](../mfc/reference/chotkeyctrl-class.md#setrules). Для элементов управления в диалоговом окне, настало время сделать это — в поле диалогового окна [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) функции.  
  
-   Пользователь взаимодействует с элементом управления, нажав сочетание клавиш горячей при активном ключевой элемент управления имеет фокус. Пользователь затем каким-либо образом указывает, что задача завершена, возможно, нажав кнопку в диалоговом окне.  
  
-   Если программа получает уведомление о том, что пользователь выбрал сочетания клавиш, следует использовать функцию-член [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) для получения виртуального значения состояния сдвига и ключ из горячей ключа элемента управления.  
  
-   Если известно, какой ключ выбранный пользователем, можно задать сочетание клавиш, с помощью одного из методов, описанных в [задание сочетания клавиш](../mfc/setting-a-hot-key.md).  
  
-   Если горячей ключевой элемент управления в диалоговом окне, его и `CHotKeyCtrl` объект будет удален автоматически. Если нет, необходимо убедиться, что оба элемента управления и `CHotKeyCtrl` правильно удаляется объект.  
  
## <a name="see-also"></a>См. также  
 [Использование CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

