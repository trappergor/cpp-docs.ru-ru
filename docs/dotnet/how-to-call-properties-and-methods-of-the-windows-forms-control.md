---
title: 'Как: вызов свойств и методов элемента Windows Forms управления | Документация Майкрософт'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- method calls, Windows Forms
- calling methods, Windows Forms control
- calling properties, Windows Forms control
- Windows Forms controls [C++], methods
- calling properties
- Windows Forms controls [C++], properties
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1d3f8dc2251dbfbcd8155b0edc512a9dc40bacc2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393403"
---
# <a name="how-to-call-properties-and-methods-of-the-windows-forms-control"></a>Практическое руководство. Вызов свойств и методов элемента управления Windows Forms

Так как [CWinFormsView::GetControl](../mfc/reference/cwinformsview-class.md#getcontrol) возвращает указатель на <xref:System.Windows.Forms.Control?displayProperty=fullName>, а не указатель на `WindowsControlLibrary1::UserControl1`, рекомендуется добавить элемент пользовательского типа элемента управления и инициализировать его в [IView::OnInitialUpdate ](../mfc/reference/iview-interface.md#oninitialupdate). Теперь можно вызвать методы и свойства с помощью `m_ViewControl`.

В этом разделе предполагается, вы выполнили ранее [как: Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) и [как: Создание пользовательского элемента управления и представление главного приложения MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

### <a name="to-create-the-mfc-host-application"></a>Создание ведущего приложения MFC

1. Откройте приложение MFC, созданное в [как: Создание пользовательского элемента управления и представление главного приложения MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

1. Добавьте следующую строку в раздел общих переопределения `CMFC02View` объявление в MFC02View.h класса.

     `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`

1. Добавьте переопределение для OnInitialupdate.

     Отображение **свойства** окно (F4). В **представление классов** (CTRL + SHIFT + C), выберите класс CMFC02View. В **свойства** окно, выберите значок для переопределений. Прокрутки вниз по списку, чтобы OnInitialUpdate. Щелкните раскрывающийся список и выберите \<Добавить >. В MFC02View.cpp. Убедитесь, что тело функции OnInitialUpdate выглядит следующим образом:

    ```
    CWinFormsView::OnInitialUpdate();
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());
    m_ViewControl->textBox1->Text = gcnew System::String("hi");
    ```

1. Постройте и запустите проект.

     В меню **Сборка** выберите **Собрать решение**.

     На **Отладка** меню, щелкните **Запуск без отладки**.

     Обратите внимание на то, что поле инициализируется теперь.

## <a name="see-also"></a>См. также

[Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)