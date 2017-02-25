---
title: "Viewing and Adding ActiveX Controls to a Dialog Box | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.controls.activex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dialog boxes [C++], adding ActiveX controls"
  - "Insert ActiveX Control command"
  - "ActiveX controls [C++], adding to dialog boxes"
ms.assetid: e1c2e3ae-e1b0-40d3-9766-623007073856
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Viewing and Adding ActiveX Controls to a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Среда разработки Visual Studio позволяет вставлять элементы ActiveX в диалоговое окно.  
  
### Просмотр доступных элементов ActiveX  
  
1.  Откройте диалоговое окно в редакторе диалоговых окон.  
  
2.  Щелкните правой кнопкой мыши в области диалогового окна.  
  
3.  В контекстном меню выберите команду **Вставить элемент ActiveX**.  
  
     Появится диалоговое окно [Вставка элемента ActiveX](../Topic/Insert%20ActiveX%20Control%20Dialog%20Box.md), в котором будут представлены все элементы ActiveX, доступные в системе. В нижней части диалогового окна отображается путь к файлу элемента ActiveX.  
  
### Добавление элемента ActiveX в диалоговое окно  
  
1.  В диалоговом окне [Вставка элемента ActiveX](../Topic/Insert%20ActiveX%20Control%20Dialog%20Box.md) выберите элемент, который необходимо добавить в диалоговое окно, и нажмите кнопку **ОК**.  
  
     Элемент появится в диалоговом окне, после чего его можно будет изменить или создать для него обработчики, как для любого другого элемента управления.  
  
    > [!NOTE]
    >  Элементы ActiveX можно добавить в [окно панели элементов](../Topic/Toolbox.md). Дополнительные сведения см. в разделе [Управление элементами и вкладками на панели элементов](http://msdn.microsoft.com/ru-ru/21285050-cadd-455a-b1f5-a2289a89c4db).  
  
    > [!CAUTION]
    >  Распространение всех элементов ActiveX в системе может быть незаконным. Эти вопросы освещены в лицензионном соглашении к программному обеспечению, которое обеспечивает установку элементов управления. Также можно обратиться к поставщику данного ПО.  
  
     Для упрощения доступа элементы управления можно поместить в окно панели элементов. Дополнительные сведения см. в разделе [Диалоговое окно "Настройка области элементов"](http://msdn.microsoft.com/ru-ru/bd07835f-18a8-433e-bccc-7141f65263bb).  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 Win32  
  
## См. также  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Контейнеры для элементов управления ActiveX](../mfc/activex-control-containers.md)