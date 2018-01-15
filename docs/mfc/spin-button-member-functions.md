---
title: "Функции-члены счетчика | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- spin button control, methods
- CSpinButtonCtrl class [MFC], methods
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c6f0abfd5803ea4b4d4b4478104790e0f56e5afc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="spin-button-member-functions"></a>Функции-члены счетчика
Существует несколько функций-членов для элемента управления "Счетчик" ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)). Используйте эти функции, чтобы изменить следующие атрибуты счетчиком.  
  
-   **Ускорение** можно настроить скорость, с которой изменяется положение при удерживании пользователем кнопки со стрелками. Для работы с ускорение, используйте [SetAccel](../mfc/reference/cspinbuttonctrl-class.md#setaccel) и [GetAccel](../mfc/reference/cspinbuttonctrl-class.md#getaccel) функции-члены.  
  
-   **Базовый** базы (10 или 16), используемый для отображения позиции в заголовке в связанном окне можно изменить. Для работы с базой, используйте [GetBase](../mfc/reference/cspinbuttonctrl-class.md#getbase) и [SetBase](../mfc/reference/cspinbuttonctrl-class.md#setbase) функции-члены.  
  
-   **Окно приятель** можно динамически задать в связанном окне. Чтобы запросить или изменить, какой элемент управления находится в связанном окне, используйте [GetBuddy](../mfc/reference/cspinbuttonctrl-class.md#getbuddy) и [SetBuddy](../mfc/reference/cspinbuttonctrl-class.md#setbuddy) функции-члены.  
  
-   **Позиция** могут запрашивать и изменять положение. Для работы непосредственно с позиции, используйте [GetPos](../mfc/reference/cspinbuttonctrl-class.md#getpos) и [SetPos](../mfc/reference/cspinbuttonctrl-class.md#setpos) функции-члены. Поскольку (например, в случае, контакт является элементом управления), может отличаться заголовок элемента управления контактному лицу `GetPos` извлекает текущий заголовок и соответствующим образом изменяет положение.  
  
-   **Диапазон** можно изменить максимальное и минимальное позиции для счетчиком. По умолчанию максимальное равен 0 и минимальным становится равным 100. Поскольку по умолчанию максимальное значение меньше, чем минимальное значение по умолчанию, counter-intuitive действия кнопки со стрелками. Как правило, будет задать диапазон с помощью [SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) функции-члена. Чтобы запросить использование диапазона [GetRange](../mfc/reference/cspinbuttonctrl-class.md#getrange).  
  
## <a name="see-also"></a>См. также  
 [Использование CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

