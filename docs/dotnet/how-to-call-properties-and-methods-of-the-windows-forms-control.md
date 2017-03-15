---
title: "Практическое руководство. Вызов свойств и методов элемента управления Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "вызов методов, элемент управления Windows Forms"
  - "вызов свойств"
  - "вызов свойств, элемент управления Windows Forms"
  - "вызовы метода, Windows Forms"
  - "элементы управления Windows Forms [C++], методы"
  - "элементы управления Windows Forms [C++], свойства"
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Практическое руководство. Вызов свойств и методов элемента управления Windows Forms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Поскольку [CWinFormsView::GetControl](../Topic/CWinFormsView::GetControl.md) возвращает указатель на <xref:System.Windows.Forms.Control?displayProperty=fullName>, а не на `WindowsControlLibrary1::UserControl1`, рекомендуется добавить тип пользовательского элемента управления в и инициализировать его в [IView::OnInitialUpdate](../Topic/IView::OnInitialUpdate.md).  После этого можно использовать методы и свойства с помощью `m_ViewControl`.  
  
 В этом разделе предполагается, что читатель знаком с содержанием разделов [Практическое руководство. Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) и [Практическое руководство. Создание пользовательского элемента управления и просмотр ведущего интерфейса MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
### Создание ведущего приложения MFC  
  
1.  Откройте приложение MFC, созданное в разделе [Практическое руководство. Создание пользовательского элемента управления и просмотр ведущего интерфейса MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
2.  Добавьте следующую строку к общему разделу переопределений в объявлении класса `CMFC02View` в файле MFC02View.h.  
  
     `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`  
  
3.  Добавьте переопределение для OnInitialupdate.  
  
     Откройте окно **Свойства** \(нажав клавишу F4\).  В параметре **Представлении класса** \(CTRL\+SHIFT\+C\) выберите класс CMFC02View.  В окне **Свойства** выберите значок для переопределений.  Переместитесь вниз по списку к OnInitialUpdate.  Щелкните в раскрывающемся списке и выделите \<Add\>.  В MFC02View.cpp убедитесь, что текст функции OnInitialUpdate имеет следующий вид:  
  
    ```  
    CWinFormsView::OnInitialUpdate();  
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());  
    m_ViewControl->textBox1->Text = gcnew System::String("hi");  
    ```  
  
4.  Выполните построение и запуск проекта.  
  
     В меню **Построение** выберите **Построить решение**.  
  
     В меню **Отладка** выберите команду **Запуск без отладки**.  
  
     Обратите внимание, что теперь текстовое поле инициализировано.  
  
## См. также  
 [Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)