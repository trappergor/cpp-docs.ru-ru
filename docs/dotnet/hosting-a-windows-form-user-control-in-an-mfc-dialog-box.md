---
title: Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
ms.openlocfilehash: 2704e04df3792edfee6c39f597fcbe71b6ce51b4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374484"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC

MFC размещает управление Формами Windows в качестве специального вида управления ActiveX и общается с <xref:System.Windows.Forms.Control> управлением с помощью интерфейсов ActiveX, свойств и методов класса. Мы рекомендуем использовать свойства и методы .NET Framework для работы на элементе управления.

Для примера приложения, которое показывает Windows Формы, используемые с MFC, [см.](https://www.microsoft.com/download/details.aspx?id=2113)

> [!NOTE]
> В текущем выпуске `CDialogBar` объект не может размещать элементы управления Windows Forms.

## <a name="in-this-section"></a>в этом разделе

[Практическое руководство. Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

[Как: Связывать сядки dDX/DDV с формами Windows](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

[Практическое руководство. Получение событий Windows Forms из собственных классов C++](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

## <a name="reference"></a>Справочник

[Класс CWinFormsControl](../mfc/reference/cwinformscontrol-class.md) &#124; [Класс CDialog](../mfc/reference/cdialog-class.md) &#124; [CWnd класса](../mfc/reference/cwnd-class.md) &#124;<xref:System.Windows.Forms.Control>

## <a name="see-also"></a>См. также раздел

[Использование управления пользователями формы Windows в MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Windows Формы / MFC Программирование Различия](../dotnet/windows-forms-mfc-programming-differences.md)<br/>
[Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)
