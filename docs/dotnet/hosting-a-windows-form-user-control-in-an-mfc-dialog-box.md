---
title: Размещение Windows форме пользовательского элемента управления в диалоговом окне MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 291c0856e9d305e0b2b31c6bc233005b111592a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC
Размещает элемент управления Windows Forms как особый тип элемента управления ActiveX MFC и взаимодействует с элементом управления, используя интерфейсы ActiveX и свойства и методы <xref:System.Windows.Forms.Control> класса. Мы рекомендуем использовать .NET Framework свойства и методы для работы в элементе управления.  
  
 Образец приложения Windows Forms используются с MFC, в разделе [MFC и интеграция с Windows Forms](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
> [!NOTE]
>  В текущем выпуске `CDialogBar` не может размещать элементы управления Windows Forms.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)  
  
 [Как: привязка данных DDX/DDV к элементам Управления Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)  
  
 [Практическое руководство. Получение событий Windows Forms из собственных классов C++](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)  
  
## <a name="reference"></a>Ссылка  
 [Класс CWinFormsControl](../mfc/reference/cwinformscontrol-class.md) &#124; [класса CDialog](../mfc/reference/cdialog-class.md) &#124; [класс CWnd](../mfc/reference/cwnd-class.md)&#124; <xref:System.Windows.Forms.Control>  
  
## <a name="see-also"></a>См. также  
 [Использование пользовательского элемента управления формы Windows в MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Различия в программировании Windows Forms/MFC](../dotnet/windows-forms-mfc-programming-differences.md)   
 [Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)