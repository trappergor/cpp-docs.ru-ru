---
title: 'TN006: Схемы сообщений | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.messages.maps
dev_langs:
- C++
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- ON_NOTIFY_RANGE macro [MFC]
- ON_COMMAND macro [MFC]
- ON_CONTROL_RANGE macro [MFC]
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_NOTIFY message [MFC]
- ON_COMMAND_RANGE_EX macro [MFC]
- ON_MESSAGE macro [MFC]
- Windows messages [MFC], message maps
- ON_COMMAND_RANGE macro [MFC]
- TN006
- ON_CONTROL macro [MFC]
- ON_COMMAND_EX macro [MFC]
- message maps [MFC], Windows messaging
ms.assetid: af4b6794-4b40-4f1e-ad41-603c3b7409bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 160b88a7069ac9a5851c0f472f756d694e59874e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384701"
---
# <a name="tn006-message-maps"></a>TN006. Схемы сообщений
Эта заметка описывает функцию карты сообщений MFC.  
  
## <a name="the-problem"></a>Проблема  
 Microsoft Windows реализует виртуальные функции в классы окон, использующие его средства обмена сообщениями. Из-за большого числа сообщений, участвующих предоставление отдельные виртуальные функции для каждого сообщения Windows создаст чрезмерно большим vtable.  
  
 Так как количество системных сообщений Windows меняются с течением времени, и потому, что приложения могут определять свои собственные сообщения Windows, схемы сообщений обеспечивают уровень косвенности, который предотвращает изменения интерфейса нарушения существующего кода.  
  
## <a name="overview"></a>Обзор  
 MFC предоставляет альтернативный способ для оператора switch, который использовался в традиционных программ Windows для обработки сообщений, отправляемых в окно. Сопоставление сообщений методов можно задать, чтобы автоматически при получении сообщения окна, вызывается соответствующий метод. Эта функция позволяет схемы сообщений разработан напоминают виртуальные функции, но обеспечивает дополнительные преимущества, невозможно использовать с виртуальными функциями C++.  
  
## <a name="defining-a-message-map"></a>Определение схемы сообщений  
 [DECLARE_MESSAGE_MAP](reference/message-map-macros-mfc.md#declare_message_map) макрос объявляет три члена класса.  
  
-   Закрытый массив `AFX_MSGMAP_ENTRY` записи с названием `_messageEntries`.  
  
-   Защищенный `AFX_MSGMAP` структуры, которая называется `messageMap` , указывающий `_messageEntries` массива.  
  
-   Защищенная виртуальная функция, вызываемая `GetMessageMap` , возвращает адрес `messageMap`.  
  
 Этот макрос должен быть помещен в объявлении класса, с помощью схемы сообщений. По соглашению это в конце объявления класса. Пример:  
  
```  
class CMyWnd : public CMyParentWndClass  
{ *// my stuff...  
 
protected: *//{{AFX_MSG(CMyWnd)  
    afx_msg void OnPaint();
*//}}AFX_MSG  
 
    DECLARE_MESSAGE_MAP() 
};  
```  
  
 Это формат, созданные AppWizard и ClassWizard при создании новых классов. / / {{И / или}} квадратные скобки необходимы для классов.  
  
 Таблицы в схеме сообщений определяется с помощью набор макросов, которые можно развернуть для записи схемы сообщений. Таблица начинается со [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) вызов макроса, который определяет класс, которое обрабатывается этой схеме сообщений и родительского класса, на который передаются необработанных сообщений. Таблица заканчивается [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) вызов макроса.  
  
 Между вызовами этих двух макрос — это запись для каждого сообщения должны обрабатываться этой схеме сообщений. Каждый стандартных сообщений Windows имеют макрос формы ON_WM_*MESSAGE_NAME* , создает запись для этого сообщения.  
  
 Подпись стандартной функции был определен для распаковки параметров каждого сообщения Windows и обеспечивая безопасность типов. Эти подписи можно найти в файле Afxwin.h в объявлении объекта [CWnd](../mfc/reference/cwnd-class.md). Каждый из них помечен с помощью ключевого слова `afx_msg` для упрощения идентификации.  
  
> [!NOTE]
>  Мастер классов необходимо использовать `afx_msg` ключевое слово в объявлениях обработчика сообщений карты.  
  
 Эти функции подписи был получен с помощью простого соглашения. Имя функции всегда начинается с `"On`». Это следуют имя Windows для этого сообщения WM_» «удалить и первой буквы каждого слова прописными буквами. Порядок параметров имеет `wParam` следуют `LOWORD`(`lParam`) затем `HIWORD`(`lParam`). Неиспользуемые параметры не передаются. Все дескрипторы, которые являются оболочкой для классов MFC, преобразуются в указатели на соответствующие объекты MFC. В следующем примере показано, как обрабатывать `WM_PAINT` сообщение и вызвать `CMyWnd::OnPaint` вызывать функцию:  
  
```  
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass) *//{{AFX_MSG_MAP(CMyWnd)  
    ON_WM_PAINT() *//}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 Таблица карты сообщений должны быть определены за пределами области любого определения класса или функции. Его не следует размещать в блоке extern «C».  
  
> [!NOTE]
>  ClassWizard изменит записи схемы сообщений, которые происходят между / / {{и / или}} комментарий квадратную скобку.  
  
## <a name="user-defined-windows-messages"></a>Определяемые пользователем сообщения Windows  
 Пользовательские сообщения могут быть включены в схему сообщений с помощью [ON_MESSAGE](reference/message-map-macros-mfc.md#on_message) макрос. Этот макрос принимает номер сообщения и метод формы:  
  
"" * / / внутри объявления класса  
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

 
 #<a name="define-wmmymessage-wmuser--100"></a>Определение WM_MYMESSAGE (WM_USER + 100)  
 
BEGIN_MESSAGE_MAP (CMyWnd, CMyParentWndClass)  
    ON_MESSAGE (WM_MYMESSAGE, OnMyMessage)  
END_MESSAGE_MAP()  
```  
  
 In this example, we establish a handler for a custom message that has a Windows message ID derived from the standard `WM_USER` base for user-defined messages. The following example shows how to call this handler:  
  
```  
CWnd * pWnd =...;  
pWnd -> SendMessage(WM_MYMESSAGE);
```  
  
 The range of user-defined messages that use this approach must be in the range `WM_USER` to 0x7fff.  
  
> [!NOTE]
>  ClassWizard does not support entering `ON_MESSAGE` handler routines from the ClassWizard user interface. You must manually enter them from the Visual C++ editor. ClassWizard will parse these entries and let you browse them just like any other message-map entries.  
  
## Registered Windows Messages  
 The [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) function is used to define a new window message that is guaranteed to be unique throughout the system. The macro `ON_REGISTERED_MESSAGE` is used to handle these messages. This macro accepts a name of a `UINT NEAR` variable that contains the registered windows message ID. For example  
  
```  
Класс CMyWnd: открытого CMyParentWndClass  
{  
public:  
    CMyWnd();

 *//{{AFX_MSG(CMyWnd)  
    afx_msg LRESULT OnFind(WPARAM wParam, LPARAM lParam); * //}}AFX_MSG  
 
    DECLARE_MESSAGE_MAP() 
};  
 
статические UINT РЯДОМ WM_FIND = RegisterWindowMessage("COMMDLG_FIND");

 
*//{{AFX_MSG_MAP(CMyWnd) BEGIN_MESSAGE_MAP (CMyWnd, CMyParentWndClass)  
    ON_REGISTERED_MESSAGE (WM_FIND, OnFind) * //}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 The registered Windows message ID variable (WM_FIND in this example) must be a `NEAR` variable because of the way `ON_REGISTERED_MESSAGE` is implemented.  
  
 The range of user-defined messages that use this approach will be in the range 0xC000 to 0xFFFF.  
  
> [!NOTE]
>  ClassWizard does not support entering `ON_REGISTERED_MESSAGE` handler routines from the ClassWizard user interface. You must manually enter them from the text editor. ClassWizard will parse these entries and let you browse them just like any other message-map entries.  
  
## Command Messages  
 Command messages from menus and accelerators are handled in message maps with the `ON_COMMAND` macro. This macro accepts a command ID and a method. Only the specific `WM_COMMAND` message that has a `wParam` equal to the specified command ID is handled by the method specified in the message-map entry. Command handler member functions take no parameters and return `void`. The macro has the following form:  
  
```  
ON_COMMAND (идентификатор, memberFxn)  
```  
  
 Command update messages are routed through the same mechanism, but use the `ON_UPDATE_COMMAND_UI` macro instead. Command update handler member functions take a single parameter, a pointer to a [CCmdUI](../mfc/reference/ccmdui-class.md) object, and return `void`. The macro has the form  
  
```  
ON_UPDATE_COMMAND_UI (идентификатор, memberFxn)  
```  
  
 Advanced users can use the `ON_COMMAND_EX` macro, which is an extended form of command message handlers. The macro provides a superset of the `ON_COMMAND` functionality. Extended command-handler member functions take a single parameter, a `UINT` that contains the command ID, and return a `BOOL`. The return value should be `TRUE` to indicate that the command has been handled. Otherwise routing will continue to other command target objects.  
  
 Examples of these forms:  
  
-   Inside Resource.h (usually generated by Visual C++)  
  
 ```  
 #<a name="define----idmycmd------100"></a>Определение ID_MYCMD 100  
 #<a name="define----idcomplex----101"></a>Определение ID_COMPLEX 101  
 ```  
  
-   Inside the class declaration  
  
 ```  
    afx_msg void OnMyCommand();
afx_msg void OnUpdateMyCommand (CCmdUI * pCmdUI);

    afx_msg BOOL OnComplexCommand(UINT nID);

 ```  
  
-   Inside the message map definition  
  
 ```  
    ON_COMMAND(ID_MYCMD,
    OnMyCommand)  
    ON_UPDATE_COMMAND_UI(ID_MYCMD,
    OnUpdateMyCommand)  
    ON_COMMAND_EX(ID_MYCMD,
    OnComplexCommand)  
 ```  
  
-   In the implementation file  
  
 ```  
    void CMyClass::OnMyCommand()  
 {* / / обработать команду  
 }  
 
    void CMyClass::OnUpdateMyCommand(CCmdUI* pCmdUI)  
 {* / / set состояние пользовательского интерфейса с pCmdUI  
 }  
 
    BOOL CMyClass::OnComplexCommand(UINT nID)  
 {* / / обработать команду  
    Возвращает значение TRUE;  
 }  
 ```  
  
 Advanced users can handle a range of commands by using a single command handler: [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range) or `ON_COMMAND_RANGE_EX`. See the product documentation for more information about these macros.  
  
> [!NOTE]
>  ClassWizard supports creating `ON_COMMAND` and `ON_UPDATE_COMMAND_UI` handlers, but it does not support creating `ON_COMMAND_EX` or `ON_COMMAND_RANGE` handlers. However, Class Wizard will parse and let you browse all four command handler variants.  
  
## Control Notification Messages  
 Messages that are sent from child controls to a window have an extra bit of information in their message map entry: the control's ID. The message handler specified in a message map entry is called only if the following conditions are true:  
  
-   The control notification code (high word of `lParam`), such as BN_CLICKED, matches the notification code specified in the message-map entry.  
  
-   The control ID (`wParam`) matches the control ID specified in the message-map entry.  
  
 Custom control notification messages may use the [ON_CONTROL](reference/message-map-macros-mfc.md#on_control) macro to define a message map entry with a custom notification code. This macro has the form  
  
```  
ON_CONTROL (wNotificationCode, идентификатор, memberFxn)  
```  
  
 For advanced usage [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range) can be used to handle a specific control notification from a range of controls with the same handler.  
  
> [!NOTE]
>  ClassWizard does not support creating an `ON_CONTROL` or `ON_CONTROL_RANGE` handler in the user interface. You must manually enter them with the text editor. ClassWizard will parse these entries and let you browse them just like any other message map entries.  
  
 The Windows Common Controls use the more powerful [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) for complex control notifications. This version of MFC has direct support for this new message by using the `ON_NOTIFY` and `ON_NOTIFY_RANGE` macros. See the product documentation for more information about these macros.  
  
## See Also  
 [Technical Notes by Number](../mfc/technical-notes-by-number.md)   
 [Technical Notes by Category](../mfc/technical-notes-by-category.md)

