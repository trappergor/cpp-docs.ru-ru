---
title: "Как: вызов свойств и методов в Windows Forms управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- method calls, Windows Forms
- calling methods, Windows Forms control
- calling properties, Windows Forms control
- Windows Forms controls [C++], methods
- calling properties
- Windows Forms controls [C++], properties
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 28e6d025d6c2aa485b5687117d64afeb7e402a79
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-call-properties-and-methods-of-the-windows-forms-control"></a>Практическое руководство. Вызов свойств и методов элемента управления Windows Forms
Так как [CWinFormsView::GetControl](../mfc/reference/cwinformsview-class.md#getcontrol) возвращает указатель на <xref:System.Windows.Forms.Control?displayProperty=fullName>, а не указатель `WindowsControlLibrary1::UserControl1`, то рекомендуется добавить член типа пользовательских элементов управления и инициализировать его в [IView::OnInitialUpdate ](../mfc/reference/iview-interface.md#oninitialupdate). После этого можно использовать методы и свойства с помощью `m_ViewControl`.  
  
 В этом разделе предполагается, вы выполнили ранее [как: Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) и [как: Создание пользовательского элемента управления и просмотр ведущего интерфейса MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
### <a name="to-create-the-mfc-host-application"></a>Создание ведущего приложения MFC  
  
1.  Откройте приложение MFC, созданные в [как: Создание пользовательского элемента управления и просмотр ведущего интерфейса MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
2.  Добавьте следующую строку в раздел общих переопределения `CMFC02View` объявления в файле MFC02View.h класса.  
  
     `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`  
  
3.  Добавьте переопределение для OnInitialupdate.  
  
     Отображение **свойства** окна (F4). В **представление классов** (CTRL + SHIFT + C), выберите класс CMFC02View. В **свойства** окно, выберите значок для переопределений. Прокрутки вниз по списку, чтобы OnInitialUpdate. Щелкните раскрывающийся список и выберите \<Добавить >. В MFC02View.cpp. Убедитесь, что тело функции OnInitialUpdate таков:  
  
    ```  
    CWinFormsView::OnInitialUpdate();  
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());  
    m_ViewControl->textBox1->Text = gcnew System::String("hi");  
    ```  
  
4.  Постройте и запустите проект.  
  
     В меню **Сборка** выберите **Собрать решение**.  
  
     На **отладки** меню, нажмите кнопку **Запуск без отладки**.  
  
     Обратите внимание, что текстовое поле теперь инициализирован.  
  
## <a name="see-also"></a>См. также  
 [Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)