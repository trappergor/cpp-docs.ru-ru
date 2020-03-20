---
title: Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
ms.openlocfilehash: bf91730f98685935d50ee0076739b436e8d9da60
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "79544787"
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC

MFC использует класс Квинформсвиев для размещения пользовательского элемента управления Windows Forms в представлении MFC. Представления Windows Forms MFC — это элементы управления ActiveX. Пользовательский элемент управления размещается как дочерний для собственного представления и занимает всю клиентскую область собственного представления.

Конечный результат напоминает модель, используемую [классом CFormView](../mfc/reference/cformview-class.md). Это позволяет использовать преимущества конструктора Windows Forms и среды выполнения для создания расширенных представлений на основе форм.

Так как представления MFC Windows Forms являются элементами управления ActiveX, они не имеют тех же `hwnd`, что и представления MFC. Они также не могут быть переданы в виде указателя на представление [CView](../mfc/reference/cview-class.md) . Как правило, используйте .NET Framework методы для работы с представлениями Windows Forms и не зависеть от Win32.

Пример приложения, в котором показаны Windows Forms, используемые в MFC, см. в разделе [Интеграция MFC и Windows Forms](https://www.microsoft.com/download/details.aspx?id=2113).

## <a name="in-this-section"></a>в этом разделе

[Практическое руководство. Создание пользовательского элемента управления и просмотр ведущего интерфейса MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)

[Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

[Практическое руководство. Вызов свойств и методов элемента управления Windows Forms](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)

## <a name="see-also"></a>См. также:

[Использование пользовательского элемента управления формы Windows Forms в MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Практическое руководство. Создание составных элементов управления](/dotnet/framework/winforms/controls/how-to-author-composite-controls)
