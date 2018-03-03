---
title: "Объявление переменной на основании нового класса элемента управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.classes.control.variable
dev_langs:
- C++
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5aa98f815d9f9322c11d4256c13c0c7a42b4ab66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>Объявление переменной на основании нового класса элемента управления
После создания класса элемента управления MFC, можно объявить переменную на его основе. Чтобы обеспечить контекст для новой переменной, необходимо открыть редактор диалоговых окон и изменить диалоговое окно, в котором вы хотите использовать элемент управления. Кроме того диалоговое окно должно быть класс, связанный с ним. Сведения об использовании редактора диалоговых окон см. в разделе [редактор диалоговых окон](../../windows/dialog-editor.md).  
  
### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>Для объявления переменной на основании повторно используемого класса  
  
1.  При редактировании диалоговое окно, перетащите элемент управления того же типа, как базовый класс нового элемента управления из панели элементов в диалоговом окне.  
  
2.  Наведите указатель мыши на перетащенный элемент управления.  
  
3.  Удерживая нажатой клавишу CTRL, дважды щелкните элемент управления.  
  
     [Добавление переменной-члена](../../ide/add-member-variable-wizard.md) откроется диалоговое окно.  
  
4.  В **доступа** выберите правильные права доступа для элемента управления.  
  
5.  Нажмите кнопку **управляющей переменной** флажок.  
  
6.  В **имя переменной** введите имя.  
  
7.  В разделе **категории**, нажмите кнопку **управления**.  
  
8.  В **идентификатор элемента управления** списка, выберите элемент управления, который был добавлен. **Тип переменной** в списке должен отобразиться соответствующий тип переменной и **типа элемента управления** управления правильный тип.  
  
9. В **комментарий** добавьте любые комментарии, будет отображаться в коде.  
  
10. Нажмите кнопку **ОК**.  
  
## <a name="see-also"></a>См. также  
 [Сопоставление сообщений с функциями](../../mfc/reference/mapping-messages-to-functions.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../../ide/adding-a-class-visual-cpp.md)   
 [Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)
