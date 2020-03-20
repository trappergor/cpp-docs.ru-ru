---
title: Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
ms.openlocfilehash: 8925b86a5920df6a53a2625b782cf41e1a7fe32c
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "79544793"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC

MFC размещает элемент управления Windows Forms как Специальный тип элемента управления ActiveX и взаимодействует с элементом управления с помощью интерфейсов ActiveX, а также свойств и методов класса <xref:System.Windows.Forms.Control>. Для работы с элементом управления рекомендуется использовать свойства и методы .NET Framework.

Пример приложения, в котором показаны Windows Forms, используемые в MFC, см. в разделе [Интеграция MFC и Windows Forms](https://www.microsoft.com/download/details.aspx?id=2113).

> [!NOTE]
>  В текущем выпуске объект `CDialogBar` не может содержать элементы управления Windows Forms.

## <a name="in-this-section"></a>в этом разделе

[Практическое руководство. Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

[Инструкции. Привязка данных DDX/DDV с помощью Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

[Практическое руководство. Получение событий Windows Forms из собственных классов C++](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

## <a name="reference"></a>Ссылки

&#124; [CWnd Class](../mfc/reference/cwnd-class.md) &#124; [CDialog Class](../mfc/reference/cdialog-class.md) [CWinFormsControl Class](../mfc/reference/cwinformscontrol-class.md) &#124; Класс квинформсконтрол класса класс класса CWnd <xref:System.Windows.Forms.Control>

## <a name="see-also"></a>См. также:

[Использование пользовательского элемента управления формы Windows Forms в MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Различия в программировании Windows Forms и MFC](../dotnet/windows-forms-mfc-programming-differences.md)<br/>
[Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)
