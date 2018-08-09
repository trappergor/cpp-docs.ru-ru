---
title: Определение переменных-членов для элементов управления диалоговых окон | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog editor, defining member variables for controls
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e1f5cee3bf827effc7c99dd66d7dc2898c9ad55f
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645468"
---
# <a name="defining-member-variables-for-dialog-controls"></a>Определение переменных-членов для элементов управления диалоговых окон
Для определения переменных-членов для всех элементов управления диалогового окна кроме кнопок можно использовать следующий метод.  
  
> [!NOTE]
>  Метод, описанный в этой статье, применим только к элементам управления диалогового окна в составе проекта MFC. Проекты ATL должны использовать **новые сообщения Windows и обработчики событий** диалоговое окно.  
  
### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>Определение переменной-члена для элемента управления диалогового окна (кроме кнопки)  
  
1.  В [редактор диалоговых окон](../windows/dialog-editor.md), выберите элемент управления.  
  
2.  Удерживая нажатой клавишу **Ctrl** , дважды щелкните управления диалогового окна.  
  
     [Мастер добавления переменной-члена](../ide/add-member-variable-wizard.md) отображается.  
  
3.  Введите соответствующие сведения в **Добавление переменной-члена** мастера. Дополнительные сведения см. в разделе [обмен данными диалоговых окон](../mfc/dialog-data-exchange.md).  
  
4.  Нажмите кнопку **ОК** для возврата **диалоговое окно** редактора.  
  
    > [!TIP]
    >  Чтобы перейти из любого элемента управления диалогового окна к его обработчику, дважды щелкните элемент управления.  
  
 Можно также использовать **переменных-членов** вкладке **мастер классов MFC** добавлять новые переменные-члены для заданного класса и просмотреть те, которые уже были определены.  
  
## <a name="requirements"></a>Требования  
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