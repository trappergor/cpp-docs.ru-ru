---
title: "Определение переменных-членов для элементов управления диалоговых окон | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog editor, defining member variables for controls
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eb966459695eb048943a12e33c8e909f99fdc92b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="defining-member-variables-for-dialog-controls"></a>Определение переменных-членов для элементов управления диалоговых окон
Для определения переменных-членов для всех элементов управления диалогового окна кроме кнопок можно использовать следующий метод.  
  
> [!NOTE]
>  Метод, описанный в этой статье, применим только к элементам управления диалогового окна в составе проекта MFC. Проекты ATL используют **новые сообщения Windows и обработчики событий** диалоговое окно.  
  
### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>Определение переменной-члена для элемента управления диалогового окна (кроме кнопки)  
  
1.  В [редактор диалоговых окон](../windows/dialog-editor.md), выберите нужный элемент управления.  
  
2.  Удерживая нажатой **CTRL** ключа, дважды щелкните элемент управления диалогового окна.  
  
     [Мастера добавления переменной-члена](../ide/add-member-variable-wizard.md) отображается.  
  
3.  Введите соответствующую информацию в **Добавление переменной-члена** мастера. Дополнительные сведения см. в разделе [обмен данными диалоговых окон](../mfc/dialog-data-exchange.md).  
  
4.  Нажмите кнопку **ОК** чтобы вернуться в редактор диалоговых окон.  
  
    > [!TIP]
    >  Чтобы перейти из любого элемента управления диалогового окна к его обработчику, дважды щелкните элемент управления.  
  

  
 Можно также использовать **переменных-членов** вкладке **мастер классов MFC** добавить новые переменные-члены для заданного класса, и просмотреть те, которые уже были определены.  
  
 Требования  
  
 MFC  
  
## <a name="see-also"></a>См. также  
 [Сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Мастер классов MFC](../mfc/reference/mfc-class-wizard.md)   
 [Добавление класса](../ide/adding-a-class-visual-cpp.md)   
 [Добавление функции-члена](../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Обработчик сообщений MFC](../mfc/reference/adding-an-mfc-message-handler.md)

