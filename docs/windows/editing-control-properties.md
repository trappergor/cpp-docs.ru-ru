---
title: "Изменение свойств элемента управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls, editing properties
ms.assetid: 9bdae21d-6dec-4344-a197-2ca4fc46d040
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d69f7f22b2bf3e51e2afa2ed53b04aeefe6a59e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="editing-control-properties"></a>Изменение свойств элемента управления
### <a name="to-edit-the-properties-of-a-control-or-controls"></a>Чтобы изменить свойства элемента управления или элементы управления  
  
1.  В диалоговом окне выберите элемент управления, который требуется изменить.  
  
    > [!NOTE]
    >  Если выбрано несколько элементов управления, можно изменить только свойства, общие для выбранных элементов управления.  
  
2.  В [окно свойств](/visualstudio/ide/reference/properties-window), изменение свойств элемента управления.  
  
    > [!NOTE]
    >  При задании **растрового изображения** свойства кнопки, переключатель или управления «флажок» равно **True**, стиль BS_BITMAP реализуется для элемента управления. Дополнительные сведения см. в разделе [стили кнопок](../mfc/reference/styles-used-by-mfc.md#button-styles). Пример сопоставления растрового изображения с элементом управления см. в разделе [CButton::SetBitmap](../mfc/reference/cbutton-class.md#setbitmap). Растровые изображения будет присутствовать в элемент управления, пока вы находитесь в редакторе ресурсов диалогового окна.  
  
### <a name="to-undo-changes-to-the-properties-of-a-control"></a>Чтобы отменить изменения свойств элемента управления  
  
1.  Убедитесь, что элемент управления имеет фокус в редакторе диалоговых окон.  
  
2.  Выберите **отменить** из **изменить** меню (если фокус установлен не на элемент управления **отменить** команда будет недоступна).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* . Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6);  
  
 Требования  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)

