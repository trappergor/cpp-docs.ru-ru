---
title: "Размещение пользовательского элемента управления  формы Windows Forms в диалоговом окне MFC | Microsoft Docs"
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
  - "размещение элемента управления Windows Forms [C++]"
  - "MFC [C++], поддержка Windows Forms"
  - "Windows Forms [C++], поддержка MFC"
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Размещение пользовательского элемента управления  формы Windows Forms в диалоговом окне MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC размещает элемент управления формы Windows Forms в виде особого элемента управления ActiveX и осуществляет связь с элементом управления посредством интерфейса ActiveX, а также свойств и методов класса <xref:System.Windows.Forms.Control>.  При использовании элемента управления рекомендуется использовать свойства и методы платформы .NET Framework.  
  
 Пример приложения, где демонстрируется использование Windows Forms с MFC, см. в разделе [MFC and Windows Forms Integration](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
> [!NOTE]
>  В данном выпуске объект `CDialogBar` не может размещать элементы управления Windows Forms.  
  
## В этом подразделе  
 [Практическое руководство. Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)  
  
 [Практическое руководство. Привязка данных DDX\/DDV к элементам управления Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)  
  
 [Практическое руководство. Получение событий Windows Forms из собственных классов C\+\+](../Topic/How%20to:%20Sink%20Windows%20Forms%20Events%20from%20Native%20C++%20Classes.md)  
  
## Ссылка  
 [CWinFormsControl Class](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog Class](../mfc/reference/cdialog-class.md) &#124; [Класс CWnd](../Topic/CWnd%20Class.md) &#124; <xref:System.Windows.Forms.Control>  
  
## См. также  
 [Использование пользовательского элемента управления формы Windows Form в MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Различия в программировании Windows Forms\/MFC](../dotnet/windows-forms-mfc-programming-differences.md)   
 [Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC](../Topic/Hosting%20a%20Windows%20Form%20User%20Control%20as%20an%20MFC%20Dialog%20Box.md)