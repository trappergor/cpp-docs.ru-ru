---
title: "Как: получение событий Windows Forms из собственных классов C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d51cc4caa7a1018e85cc880cf45894abc861d250
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-sink-windows-forms-events-from-native-c-classes"></a>Практическое руководство. Получение событий Windows Forms из собственных классов C++
Вы можете включить собственных классов C++ для получения обратных вызовов от управляемых событий, вызванных из элементов управления Windows Forms или другие формы с форматированием сопоставления макроса MFC. Получение событий в представлениях и диалоговых окнах аналогично выполнению задачи для элементов управления.  
  
 Чтобы сделать это, необходимо:  
  
-   Присоединение `OnClick` обработчик событий для элемента управления с помощью [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate).  
  
-   Создайте сопоставление делегатов с помощью [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map), [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map), и [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry).  
  
 Пример продолжает работу, начатую в [как: выполните DDX/DDV привязки данных, с помощью Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md).  
  
 Теперь будет связывать элемент управления библиотеки MFC (`m_MyControl`) с управляемым делегатом обработчика событий вызывается `OnClick` управляемого <xref:System.Windows.Forms.Control.Click> событий.  
  
### <a name="to-attach-the-onclick-event-handler"></a>Присоединение обработчика событий OnClick.  
  
1.  Добавьте следующий код для реализации BOOL CMFC01Dlg::OnInitDialog:  
  
    ```  
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );  
    ```  
  
2.  Добавьте следующий код в общий раздел объявления класса CMFC01Dlg: общий CDialog.  
  
    ```  
    // delegate map  
    BEGIN_DELEGATE_MAP( CMFC01Dlg )  
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )  
    END_DELEGATE_MAP()  
  
    void OnClick( System::Object^ sender, System::EventArgs^ e );  
    ```  
  
3.  Наконец, добавьте реализацию `OnClick` в файл CMFC01Dlg.cpp:  
  
    ```  
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)  
    {  
        AfxMessageBox(_T("Button clicked"));  
    }  
    ```  
  
## <a name="see-also"></a>См. также  
 [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)   
 [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)   
 [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)   
 [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)