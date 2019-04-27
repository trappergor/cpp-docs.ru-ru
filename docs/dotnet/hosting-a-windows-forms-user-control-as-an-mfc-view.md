---
title: Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
ms.openlocfilehash: 9c59f28739ab94210c16bd800a48997f3f2282df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222875"
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC

MFC использует класс CWinFormsView разместить пользовательский элемент управления Windows Forms в представления MFC. Представления MFC Windows Forms являются элементами управления ActiveX. Пользовательский элемент управления размещен как управляющий является потомком собственного представления и занимает всю клиентскую область собственного представления.

Конечный результат напоминает модели, используемой [класс CFormView](../mfc/reference/cformview-class.md). Это позволяет воспользоваться преимуществами конструктора Windows Forms и среды выполнения для создания расширенных представлений на основе форм.

Так как представления MFC Windows Forms являются элементами управления ActiveX, у которых нет же `hwnd` как представления MFC. Также они могут передаваться как указатель на [CView](../mfc/reference/cview-class.md) представления. Как правило использование методов .NET Framework для работы с представлениями Windows Forms и уменьшения Win32.

Образец приложения, Windows Forms с MFC, см. в разделе [MFC и Windows Forms Integration](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).

## <a name="in-this-section"></a>В этом разделе

[Практическое руководство. Создание пользовательского элемента управления и просмотр ведущего интерфейса MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)

[Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

[Практическое руководство. Вызов свойств и методов элемента управления Windows Forms](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)

## <a name="see-also"></a>См. также

[Использование пользовательского элемента управления формы Windows Forms в MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Практическое руководство. Создание составных элементов управления](/dotnet/framework/winforms/controls/how-to-author-composite-controls)
