---
title: "Custom Controls in the Dialog Editor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Custom Control"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [C++], templates"
  - "custom controls [Visual Studio], dialog boxes"
  - "custom controls [Visual Studio]"
  - "dialog box controls, custom (user) controls"
  - "Dialog editor, custom controls"
ms.assetid: f494b314-4000-4bbe-bbd0-4b18fb71ede1
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Custom Controls in the Dialog Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Редактор диалоговых окон позволяет использовать настраиваемые или пользовательские элементы управления в шаблонах диалоговых окон.  
  
> [!NOTE]
>  В данном случае пользовательские веб\-элементы управления не следует путать с элементами управления ActiveX.  Элементы управления ActiveX иногда называют пользовательскими элементами управления OLE.  Также не стоит путать эти элементы управления с элементами управления, внешний вид которых настраивается пользователем в среде Windows.  
  
 Эта функция позволяет использовать элементы управления, которые не входят в стандартный комплект Windows.  Во время выполнения элемент управления сопоставляется с классом Windows \(отличным от класса C\+\+\).  Как правило, для решения этой задачи в диалоговое окно устанавливается любой элемент управления, например статический.  Затем во время выполнения в рамках функции [OnInitDialog](../Topic/CDialog::OnInitDialog.md) этот элемент управления удаляется и вместо него добавляется пользовательский элемент управления.  
  
 Эта техника устарела.  Сегодня, как правило, рекомендуется написать элемент управления ActiveX или создать подкласс общих элементов управления Windows.  
  
 С этими элементами управления можно выполнять только следующие действия:  
  
-   Определять их положение в диалоговом окне.  
  
-   Вводить заголовок.  
  
-   Идентифицировать имя класса Windows для элемента управления \(код приложения должен зарегистрировать элемент управления по его имени\).  
  
-   Вводить 32\-битовое шестнадцатеричное значение, определяющее стиль элемента управления.  
  
-   Задавать расширенный стиль.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Требования  
 Win32  
  
## См. также  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Элементы управления](../mfc/controls-mfc.md)