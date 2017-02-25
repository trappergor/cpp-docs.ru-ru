---
title: "Отображение и скрытие панели инструментов в редакторе диалоговых окон | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления [C++], отображение или скрытие панели инструментов в редакторе диалоговых окон"
  - "панели инструментов [C++], отображение"
  - "панели инструментов [C++], скрытие"
  - "Редактор диалоговых окон, отображение или скрытие панели инструментов"
ms.assetid: 93c255e1-90eb-48b6-8602-450acda75bed
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Отображение и скрытие панели инструментов в редакторе диалоговых окон
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Когда редактор диалоговых окон открывается, панель инструментов автоматически отображается в верхней части решения.  
  
### Панель инструментов редактора диалоговых окон  
  
|Значок|Значение|Значок|Значение|  
|------------|--------------|------------|--------------|  
|![Кнопка "Проверить диалоговое окно"](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|Проверить диалоговое окно|![Кнопка "Задавать интервалы по горизонтали"](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|По горизонтали|  
|![Кнопка "Выровнять левые границы"](../Image/vcDialogEditorAlignLefts.png "vcDialogEditorAlignLefts")|Выровнять левые границы|![Кнопка "Задать интервалы по вертикали"](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|Вниз|  
|![Кнопка "Выровнять правые границы"](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|Выровнять правые границы|![Кнопка "Сделать одной ширины"](../Image/vcDialogEditorSameWidth.png "vcDialogEditorSameWidth")|Сделать одной ширины|  
|![Кнопка "Выровнять верхние границы"](../Image/vcDialogEditorAlignTops.png "vcDialogEditorAlignTops")|Выровнять верхние границы|![Кнопка "Сделать одной высоты"](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|Сделать одной высоты|  
|![Кнопка "Выровнять нижние границы"](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|Выровнять нижние границы|![Кнопка "Сделать одного размера"](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|Сделать одного размера|  
|![Кнопка "Центрировать по вертикали"](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|Вертикальный|![Кнопка "Показать сетку"](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|Сетка|  
|![Кнопка "Центрировать по горизонтали"](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|Horizontal|![Кнопка "Показать направляющие"](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|Направляющие|  
  
 Редактор диалоговых окон оснащен кнопками, которые позволяют упорядочивать элементы управления в макете диалогового окна как по размеру, так и по расположению.  Соответствующие команды есть и в меню "Формат".  Дополнительные сведения см. в разделе [Сочетания клавиш для редактора диалоговых окон](../mfc/accelerator-keys-for-the-dialog-editor.md).  
  
 Редактор диалоговых окон позволяет управлять отображением панели инструментов, которую можно выбрать в списке доступных панелей и окон.  
  
### Отображение и скрытие панели инструментов в редакторе диалоговых окон  
  
1.  В меню **Вид** выберите **Панели инструментов**, а затем выберите в подменю пункт **Редактор диалоговых окон**.  
  
    > [!NOTE]
    >  Панель инструментов редактора диалоговых окон отображается по умолчанию, когда в редакторе открывается ресурс диалогового окна. Однако, если панель будет закрыта явным образом, в следующем рабочем сеансе необходимо будет вызвать ее явным образом для работы с другим ресурсом.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 Win32  
  
## См. также  
 [Arrangement of Controls on Dialog Boxes](../mfc/arrangement-of-controls-on-dialog-boxes.md)   
 [How to: Create a Resource](../windows/how-to-create-a-resource.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Dialog Editor](../mfc/dialog-editor.md)