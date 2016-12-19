---
title: "Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "размещение элемента управления Windows Forms [C++]"
  - "MFC [C++], поддержка Windows Forms"
  - "элементы управления Windows Forms [C++], размещение как представления MFC"
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В MFC используется класс CWinFormsView для размещения пользовательского элемента управления Windows Forms в представлении MFC.  Представления Windows Forms в MFC являются элементами управления ActiveX.  Пользовательские элементы управления размещаются как дочерние элементы собственного представления и занимают всю клиентскую область собственного представления.  
  
 Конечный результат схож с моделью, используемой классом [CFormView Class](../mfc/reference/cformview-class.md).  Это позволяет воспользоваться преимуществами конструктора Windows Forms и среды выполнения для создания расширенных представлений на основе форм.  
  
 Поскольку представления Windows Forms в MFC являются элементами управления ActiveX, им необязательно иметь дескриптор `hwnd`, обязательный для представлений MFC.  Они также не могут быть переданы в качестве указателя представлению [CView](../Topic/CView%20Class.md).  В общем случае при работе с представлениями Windows Forms предпочтительным является использование методов .NET Framework, а не Win32.  
  
 Пример приложения, где демонстрируется использование Windows Forms с MFC, см. в разделе [MFC and Windows Forms Integration](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
## В этом подразделе  
 [Практическое руководство. Создание пользовательского элемента управления и просмотр ведущего интерфейса MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)  
  
 [Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)  
  
 [Практическое руководство. Вызов свойств и методов элемента управления Windows Forms](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)  
  
## См. также  
 [Использование пользовательского элемента управления формы Windows Form в MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Практическое руководство. Создание составных элементов управления](../Topic/How%20to:%20Author%20Composite%20Controls.md)