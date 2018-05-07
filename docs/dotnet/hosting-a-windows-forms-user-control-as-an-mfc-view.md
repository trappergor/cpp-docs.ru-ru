---
title: Размещение в Windows Forms пользовательского элемента управления в качестве представления MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bf9e54b3e2808a232bc13052c885a341cb51297f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC
MFC использует класс CWinFormsView для пользовательского элемента управления Windows Forms в представления MFC. Представления MFC Windows Forms, элементы управления ActiveX. Пользовательский элемент управления размещен как дочерние элементы собственного представления и занимает всю клиентскую область собственного представления.  
  
 Конечный результат напоминает модель, используемая [класс CFormView](../mfc/reference/cformview-class.md). Это позволяет воспользоваться преимуществами конструктора Windows Forms и среды выполнения для создания расширенных представлений на основе форм.  
  
 Так как представления MFC Windows Forms — элементы управления ActiveX, не имеющих одинаковое `hwnd` как представления MFC. Также они не могут быть переданы как указатель на [CView](../mfc/reference/cview-class.md) представления. Как правило использование методов .NET Framework для работы с Windows Forms представления и меньше зависят от Win32.  
  
 Образец приложения Windows Forms используются с MFC, в разделе [MFC и интеграция с Windows Forms](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Создание пользовательского элемента управления и просмотр ведущего интерфейса MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)  
  
 [Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)  
  
 [Практическое руководство. Вызов свойств и методов элемента управления Windows Forms](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)  
  
## <a name="see-also"></a>См. также  
 [Использование пользовательского элемента управления формы Windows в MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Практическое руководство. Создание составных элементов управления](/dotnet/framework/winforms/controls/how-to-author-composite-controls)