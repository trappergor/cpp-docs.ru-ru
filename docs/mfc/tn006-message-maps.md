---
title: 'TN006: Схемы сообщений | Документация Майкрософт'
ms.custom: ''
ms.date: 06/25/2018
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
ms.openlocfilehash: 69aecab15ffb1914dbc8a6a6ae15fca307bc77ef
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386256"
---
# <a name="tn006-message-maps"></a>TN006. Схемы сообщений

Эта заметка описывает функцию сопоставления сообщений MFC.

## <a name="the-problem"></a>Проблема

Microsoft Windows реализует виртуальные функции в окне классов, использующих его средства обмена сообщениями. Из-за большого количества сообщений, участвующих предоставляя отдельной виртуальной функции для каждого сообщения Windows создаст чрезмерно большим vtable.

Так как количество системных сообщений Windows меняются с течением времени, и так как приложения могут определять свои собственные сообщения Windows, схемы сообщений обеспечивают уровень косвенности, который предотвращает изменения интерфейса разрушать существующий код.

## <a name="overview"></a>Обзор

MFC предоставляет альтернативу оператора switch, который использовался в традиционных программ на основе Windows для обработки сообщений, отправленных в окно. Сопоставление сообщений для методов можно определить, когда окно получает сообщение, соответствующий метод вызывается автоматически. Эта функция позволяет схемы сообщений разработан, чтобы он напоминал виртуальные функции, но имеет дополнительные преимущества, недоступные в виртуальных функций C++.

## <a name="defining-a-message-map"></a>Определение виртуальной схемы сообщений

[DECLARE_MESSAGE_MAP](reference/message-map-macros-mfc.md#declare_message_map) макрос объявляет три члена класса.

- Вызывается частного массива записей AFX_MSGMAP_ENTRY *_messageEntries*.

- Защищенная структура AFX_MSGMAP вызывается *messageMap* , указывающий *_messageEntries* массива.

- Защищенная виртуальная функция, вызываемая `GetMessageMap` , возвращает адрес *messageMap*.

Этот макрос должны быть помещены в объявление класса, с помощью схемы сообщений. По соглашению он находится в конце объявления класса. Пример:

```cpp
class CMyWnd : public CMyParentWndClass
{
    // my stuff...

protected:
    //{{AFX_MSG(CMyWnd)
    afx_msg void OnPaint();
    //}}AFX_MSG

    DECLARE_MESSAGE_MAP()
};
```

Это формат, создаваемые AppWizard и ClassWizard при создании новых классов. / / {{И / или}} квадратные скобки необходимы для классов.

Таблицы в схеме сообщений определяется с помощью набора макросов, которые разворачиваются в записи схемы сообщений. Таблица начинается со [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) вызова макроса, который определяет класс, который обрабатывается этой схемы сообщений и родительского класса, в который передаются необработанных сообщений. Заканчивается таблице [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) вызова макроса.

Между вызовами этих двух макрос — это запись для каждого сообщения для обработки в этой схеме сообщений. Каждый стандартных сообщений Windows имеют макрос формы ON_WM_*MESSAGE_NAME* , создает запись для данного сообщения.

Подпись стандартной функции была определена для распаковка параметров каждого сообщения Windows и обеспечивая безопасность типа. Эти подписи можно найти в файле Afxwin.h в объявлении элемента [CWnd](../mfc/reference/cwnd-class.md). Каждый из них отмечается с ключевым словом **afx_msg** для упрощения идентификации.

> [!NOTE]
> ClassWizard требует использования **afx_msg** ключевое слово в объявлениях обработчика сообщений карты.

Эти сигнатуры функций были получены с помощью простого соглашения. Имя функции всегда начинается с `"On`«. Это сопровождается имя Windows для этого сообщения WM_ «» удален и первую букву каждого слова прописными буквами. Порядок параметров имеет *wParam* следуют `LOWORD`(*lParam*) затем `HIWORD`(*lParam*). Неиспользуемые параметры не передаются. Любые дескрипторы, которые помещаются в классы MFC, преобразуются в указатели на соответствующие объекты MFC. Приведенный ниже показано, как обрабатывать сообщения WM_PAINT и привести к `CMyWnd::OnPaint` функция, которая вызывается:

```cpp
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_WM_PAINT()
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

Таблица сопоставления сообщений должны быть определены за пределами области любого определения класса или функции. Его не следует размещать в блоке extern «C».

> [!NOTE]
> ClassWizard изменит записи схемы сообщений, проходящих между / / {{и / или}} комментарий скобку.

## <a name="user-defined-windows-messages"></a>Определяемые пользователем сообщения Windows

Определяемые пользователем сообщения могут быть включены в схеме сообщений, с помощью [ON_MESSAGE](reference/message-map-macros-mfc.md#on_message) макрос. Этот макрос принимает номер сообщения и метод формы:

```cpp
    // inside the class declaration
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

    #define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()
```

В этом примере мы устанавливаем обработчик пользовательское сообщение с Идентификатором сообщения Windows, производный от стандартной базового WM_USER для определяемых пользователем сообщений. В следующем примере показано, как вызывать этот обработчик:

```cpp
CWnd* pWnd = ...;
pWnd->SendMessage(WM_MYMESSAGE);
```

Диапазон определяемых пользователем сообщений, использующих этот подход должен быть в диапазоне WM_USER 0x7fff.

> [!NOTE]
> ClassWizard не поддерживает ввод подпрограммы обработчика ON_MESSAGE из ClassWizard пользовательского интерфейса. Их необходимо вручную ввести в редакторе Visual C++. ClassWizard проанализирует эти записи и позволяют просматривать их так же, как и другие записи схемы сообщений.

## <a name="registered-windows-messages"></a>Сообщения зарегистрированных Windows

[RegisterWindowMessage](https://msdn.microsoft.com/library/windows/desktop/ms644947) функция используется для определения нового сообщения окна, гарантированно будет уникальным во всей системе. Макрос ON_REGISTERED_MESSAGE используется для обработки этих сообщений. Этот макрос принимает имя *целое число без знака РЯДОМ* переменную, которая содержит идентификатор сообщения зарегистрированных windows. Пример

```cpp
class CMyWnd : public CMyParentWndClass
{
public:
    CMyWnd();

    //{{AFX_MSG(CMyWnd)
    afx_msg LRESULT OnFind(WPARAM wParam, LPARAM lParam);
    //}}AFX_MSG

    DECLARE_MESSAGE_MAP()
};

static UINT NEAR WM_FIND = RegisterWindowMessage("COMMDLG_FIND");

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

Зарегистрированный идентификатор переменная Windows сообщения (WM_FIND в этом примере), должна иметь *NEAR* переменной из-за способа реализации ON_REGISTERED_MESSAGE.

Диапазон определяемых пользователем сообщений, использующих этот подход будет находиться в диапазоне 0xC000 до 0xFFFF.

> [!NOTE]
> ClassWizard не поддерживает ввод подпрограммы обработчика ON_REGISTERED_MESSAGE из ClassWizard пользовательского интерфейса. Необходимо вручную ввести их из текстового редактора. ClassWizard проанализирует эти записи и позволяют просматривать их так же, как и другие записи схемы сообщений.

## <a name="command-messages"></a>Сообщения команды

Сообщения команды из меню и сочетания клавиш будут обрабатываться схемы сообщений с ON_COMMAND-макрос. Этот макрос принимает идентификатор команды и метод. Только определенные сообщения WM_COMMAND с *wParam* равным указанной команды, идентификатор обрабатывается с помощью метода, указанный в записи схемы сообщений. Функции-члены обработчика команды не принимают никаких параметров и возвращать **void**. Макрос имеет следующий вид:

```cpp
ON_COMMAND(id, memberFxn)
```

Команда update сообщения направляются через тот же механизм, но вместо этого использовать макрос ON_UPDATE_COMMAND_UI. Функции-члены обработчика команд обновления принимать один параметр, указатель на [CCmdUI](../mfc/reference/ccmdui-class.md) и не возвращать **void**. Макрос имеет форму

```cpp
ON_UPDATE_COMMAND_UI(id, memberFxn)
```

Опытные пользователи могут использовать on_command_ex-макрос, являющийся расширенную форму сообщения обработчиков команд. Макрос предоставляет надмножество функциональности ON_COMMAND. Функции-члены расширенного обработчика команд принимать один параметр, **UINT** , содержащее идентификатор команды и возвращать **BOOL**. Возвращаемое значение должно быть **TRUE** для указания, что команда была обработана. В противном случае маршрутизации продолжит другие целевые объекты команды.

Примеры этих форм:

- Взгляд изнутри Resource.h (как правило, создаются в Visual C++)

    ```cpp
    #define    ID_MYCMD      100
    #define    ID_COMPLEX    101
    ```

- Внутри объявления класса

    ```cpp
    afx_msg void OnMyCommand();
    afx_msg void OnUpdateMyCommand(CCmdUI* pCmdUI);
    afx_msg BOOL OnComplexCommand(UINT nID);
    ```

- Внутри определения схемы сообщений

    ```cpp
    ON_COMMAND(ID_MYCMD, OnMyCommand)
    ON_UPDATE_COMMAND_UI(ID_MYCMD, OnUpdateMyCommand)
    ON_COMMAND_EX(ID_MYCMD, OnComplexCommand)
    ```

- В файле реализации

    ```cpp
    void CMyClass::OnMyCommand()
    {
        // handle the command
    }

    void CMyClass::OnUpdateMyCommand(CCmdUI* pCmdUI)
    {
        // set the UI state with pCmdUI
    }

    BOOL CMyClass::OnComplexCommand(UINT nID)
    {
        // handle the command
        return TRUE;
    }
    ```

Опытные пользователи могут обрабатывать широкий набор команд с помощью один обработчик команды: [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range) или ON_COMMAND_RANGE_EX. Дополнительные сведения об этих макросах см.

> [!NOTE]
> ClassWizard поддерживает создание ON_COMMAND и ON_UPDATE_COMMAND_UI обработчики, но он не поддерживает создание ON_COMMAND_EX или ON_COMMAND_RANGE обработчиков. Тем не менее мастер классов проанализирует и позволяют просматривать все варианты обработчик четыре команды.

## <a name="control-notification-messages"></a>Уведомляющих сообщений элемента управления

Сообщения, отправленные из дочерних элементов управления в окно установлен дополнительный бит сведений в их сообщения сопоставить запись: идентификатор элемента управления. Обработчик сообщений, указанной в запись сопоставления сообщения вызывается только в том случае, если выполняются следующие условия:

- Код уведомления элемента управления (старшее слово *lParam*), например BN_CLICKED, соответствует код уведомления, указанный в записи схемы сообщений.

- Идентификатор элемента управления (*wParam*) совпадает с Идентификатором элемента управления, указанный в записи схемы сообщений.

Уведомляющие сообщения пользовательского элемента управления может использовать [ON_CONTROL](reference/message-map-macros-mfc.md#on_control) макрос для определения записи карты сообщение с кодом настраиваемого уведомления. Этот макрос имеет форму

```cpp
ON_CONTROL(wNotificationCode, id, memberFxn)
```

Для расширенное использование [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range) может использоваться для обработки уведомления конкретного элемента управления из диапазона элементов управления с тот же обработчик.

> [!NOTE]
> ClassWizard не поддерживает создание обработчика ON_CONTROL или ON_CONTROL_RANGE в пользовательском интерфейсе. Их необходимо вручную ввести в текстовом редакторе. ClassWizard проанализирует эти записи и позволяют просматривать их так же, как и любые другие записи схемы сообщений.

Общие элементы управления Windows использовать более эффективный [WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583) для уведомлений сложного элемента управления. Эта версия MFC имеет прямую поддержку это новое сообщение с помощью макросов ON_NOTIFY и ON_NOTIFY_RANGE. Дополнительные сведения об этих макросах см.

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)
