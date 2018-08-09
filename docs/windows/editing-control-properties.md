---
title: Изменение свойств элемента управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls, editing properties
ms.assetid: 9bdae21d-6dec-4344-a197-2ca4fc46d040
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bc7b555ee04b8739040e0ec9d53c3820c2e13f16
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648750"
---
# <a name="editing-control-properties"></a>Изменение свойств элемента управления
### <a name="to-edit-the-properties-of-a-control-or-controls"></a>Чтобы изменить свойства элемента управления или элементов управления  
  
1.  В диалоговом окне выберите элемент управления, который требуется изменить.  
  
    > [!NOTE]
    >  Если выбрано несколько элементов управления, может редактироваться только свойствами, общими для выбранных элементов управления.  
  
2.  В [окно "Свойства"](/visualstudio/ide/reference/properties-window), изменение свойств элемента управления.  
  
    > [!NOTE]
    >  При задании **точечного рисунка** свойства для кнопки, "переключатель" или управления "флажок", равным **True**, стиль для элемента управления реализуется BS_BITMAP. Дополнительные сведения см. в разделе [стили кнопок](../mfc/reference/styles-used-by-mfc.md#button-styles). Пример сопоставления растрового изображения с элементом управления, см. в разделе [CButton::SetBitmap](../mfc/reference/cbutton-class.md#setbitmap). Растровые изображения не будут отображаться на элемент управления, пока вы находитесь в **диалоговое окно** редактора ресурсов.  
  
### <a name="to-undo-changes-to-the-properties-of-a-control"></a>Чтобы отменить изменения свойств элемента управления  
  
1.  Убедитесь, что элемент управления имеет фокус **диалоговое окно** редактора.  
  
2.  Выберите **отменить** из **изменить** меню (если фокус установлен на элементе управления, не **отменить** команда будет недоступна).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Пошаговое руководство: локализация форм Windows Forms](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Пошаговое руководство: использование ресурсов для локализации с ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)