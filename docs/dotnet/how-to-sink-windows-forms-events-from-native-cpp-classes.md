---
title: Практическое руководство. Получение событий Windows Forms из собственных классов C++
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
ms.openlocfilehash: d02bcea4efce03c8fb11650d344468236737cfbd
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738783"
---
# <a name="how-to-sink-windows-forms-events-from-native-c-classes"></a>Практическое руководство. Получение событий Windows Forms из собственных классов C++

Вы можете включить собственные классы C++ для получения обратных вызовов из управляемого события, созданные из элементов управления Windows Forms или другие формы в формате MFC макрос карты. Получение событий в представлениях и диалоговых окнах аналогично выполнению задачи для элементов управления.

Чтобы сделать это, вам потребуется:

- Присоединение `OnClick` обработчик событий для элемента управления с помощью [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate).

- Создайте сопоставление делегатов с помощью [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map), [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map), и [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry).

В этом примере продолжает работу, начатую в [как: Привязка данных DDX/DDV к элементам Управления Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md).

Теперь нужно связать элемент управления MFC (`m_MyControl`) с управляемым делегатом обработчика событий вызывается `OnClick` для управляемого <xref:System.Windows.Forms.Control.Click> событий.

### <a name="to-attach-the-onclick-event-handler"></a>Чтобы настроить в обработчике события OnClick:

1. Добавьте следующий код в реализацию BOOL CMFC01Dlg::OnInitDialog:

    ```
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );
    ```

1. Добавьте следующий код в раздел public в объявлении класса CMFC01Dlg: общий CDialog.

    ```
    // delegate map
    BEGIN_DELEGATE_MAP( CMFC01Dlg )
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )
    END_DELEGATE_MAP()

    void OnClick( System::Object^ sender, System::EventArgs^ e );
    ```

1. Наконец, добавьте реализацию `OnClick` в файл CMFC01Dlg.cpp:

    ```
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)
    {
        AfxMessageBox(_T("Button clicked"));
    }
    ```

## <a name="see-also"></a>См. также

[MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)<br/>
[BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)<br/>
[END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)<br/>
[EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)
