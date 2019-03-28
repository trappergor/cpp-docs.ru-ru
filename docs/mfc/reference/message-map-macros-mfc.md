---
title: Макросы схемы сообщений (MFC)
ms.date: 03/27/2019
f1_keywords:
- AFXWIN/DECLARE_MESSAGE_MAP
- AFXWIN/BEGIN_MESSAGE_MAP
- AFXWIN/BEGIN_TEMPLATE_MESSAGE_MAP
- AFXWIN/END_MESSAGE_MAP
- AFXWIN/ON_COMMAND
- AFXWIN/ON_COMMAND_EX
- AFXWIN/ON_CONTROL
- AFXWIN/ON_MESSAGE
- AFXWIN/ON_OLECMD
- AFXWIN/ON_REGISTERED_MESSAGE
- AFXWIN/ON_REGISTERED_THREAD_MESSAGE
- AFXWIN/ON_THREAD_MESSAGE
- AFXWIN/ON_UPDATE_COMMAND_UI
- AFXWIN/ON_COMMAND_RANGE
- AFXWIN/ON_UPDATE_COMMAND_UI_RANGE
- AFXWIN/ON_CONTROL_RANGE
helpviewer_keywords:
- message map macros
- Windows messages [MFC], declaration
- demarcating Windows messages
- message maps [MFC], macros
- message maps [MFC], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
ms.openlocfilehash: b1cc721ed994ae1c6704011199ac635ee462ded8
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565545"
---
# <a name="message-map-macros-mfc"></a>Макросы схемы сообщений (MFC)

Чтобы обеспечить поддержку схемы сообщений, MFC предоставляет следующие макросы:

### <a name="message-map-declaration-and-demarcation-macros"></a>Объявление схемы сообщений и разделительной макросы

|||
|-|-|
|[DECLARE_MESSAGE_MAP](#declare_message_map)|Объявляет, что виртуальной схемы сообщений будет использоваться в классе для сопоставления сообщений к функциям (необходимо использовать в объявлении класса).|
|[BEGIN_MESSAGE_MAP](#begin_message_map)|Начинается определение виртуальной схемы сообщений (необходимо использовать в реализации класса).|
|[BEGIN_TEMPLATE_MESSAGE_MAP](#begin_template_message_map)|Начинается определение виртуальной схемы сообщений для типа класса, содержащего аргумента одного шаблона. |
|[END_MESSAGE_MAP](#end_message_map)|Завершает определение виртуальной схемы сообщений (необходимо использовать в реализации класса).|

### <a name="message-mapping-macros"></a>Макросы сопоставления сообщений

|||
|-|-|
|[ON_COMMAND](#on_command)|Указывает, какая функция будет обрабатывать сообщения указанную команду.|
|[ON_COMMAND_EX](#on_command_ex)|Указывает, какая функция будет обрабатывать сообщения указанную команду.|
|[ON_CONTROL](#on_control)|Указывает, какая функция будет обрабатывать сообщения указанного уведомление элемента управления.|
|[ON_MESSAGE](#on_message)|Указывает, какая функция будет обрабатывать определяемое пользователем сообщение.|
|[ON_OLECMD](#on_olecmd)|Указывает, какая функция будет обрабатывать команды меню из DocObject или его контейнера.|
|[ON_REGISTERED_MESSAGE](#on_registered_message)|Указывает, какая функция будет обрабатывать зарегистрированных определяемое пользователем сообщение.|
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|Указывает, какая функция будет обрабатывать зарегистрированных определяемое пользователем сообщение, при наличии `CWinThread` класса.|
|[ON_THREAD_MESSAGE](#on_thread_message)|Указывает, какая функция будет обрабатывать определяемое пользователем сообщение, когда у вас есть `CWinThread` класса.|
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|Указывает, какая функция будет обрабатывать сообщения команды обновления указанного пользовательского интерфейса.|

### <a name="message-map-range-macros"></a>Макросы схемы сообщений диапазона

|||
|-|-|
|[ON_COMMAND_RANGE](#on_command_range)|Указывает, какая функция будет обрабатывать диапазон идентификаторов, указанных в первые два параметра в макрос.|
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|Указывает, какой обработчик обновление будет обрабатывать диапазон идентификаторов, указанных в первые два параметра в макрос.|
|[ON_CONTROL_RANGE](#on_control_range)|Указывает, какая функция будет обрабатывать уведомления из диапазона идентификаторов, указанных в параметрах второго и третьего в макрос элементов управления. Первый параметр является сообщением уведомление элемента управления, например BN_CLICKED.|

Дополнительные сведения о схемы сообщений, в объявлении схемы сообщений и разделительной макросы и макросы сопоставления сообщений, см. в разделе [схемы сообщений](../../mfc/reference/message-maps-mfc.md) и [обработка сообщений и разделы сопоставления](../../mfc/message-handling-and-mapping.md). Дополнительные сведения о диапазонов схем сообщений, см. в разделе [обработчики для диапазонов схем сообщений](../../mfc/handlers-for-message-map-ranges.md).

## <a name="begin_message_map"></a> BEGIN_MESSAGE_MAP

Начинается определение схему сообщения.

### <a name="syntax"></a>Синтаксис

```
BEGIN_MESSAGE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Указывает, что имя класса, сопоставить сообщение о которой является.

*baseClass*<br/>
Указывает имя базового класса *theClass*.

### <a name="remarks"></a>Примечания

В файле реализации (CPP), который определяет функции-члены класса запуск сопоставление сообщений с begin_message_map-макрос, а затем добавить макрос записи для каждой функции обработчика сообщений и выполнить сопоставление сообщений с END_MESSAGE_MAP макрос.

Дополнительные сведения о схемах сообщений см. в разделе [схемы сообщений](message-maps-mfc.md)

### <a name="example"></a>Пример

```cpp
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="begintemplatemessagemap"></a>BEGIN_TEMPLATE_MESSAGE_MAP

Начинается определение виртуальной схемы сообщений для типа класса, содержащего аргумента одного шаблона.

### <a name="syntax"></a>Синтаксис

```
BEGIN_TEMPLATE_MESSAGE_MAP( theClass, type_name, baseClass )
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Указывает, что имя класса, сопоставить сообщение о которой является.

*type_name*<br/>
Имя параметра шаблона, указанный для класса.

*baseClass*<br/>
Указывает имя базового класса *theClass*.

### <a name="remarks"></a>Примечания

Этот макрос аналогичен [BEGIN_MESSAGE_MAP](message-map-macros-mfc.md#begin_message_map) макроса; тем не менее, этот макрос предназначен для классов, содержащий аргумент один шаблон.

В разделе реализации метода класса запустите сопоставление сообщений с макросом BEGIN_TEMPLATE_MESSAGE_MAP; затем добавьте записи макроса для каждого из методов обработчика сообщений, как это делается для карты стандартное сообщение. Как с begin_message_map-макрос, выполните сопоставление шаблона сообщений с [END_MESSAGE_MAP](message-map-macros-mfc.md#end_message_map) макрос.

Дополнительные сведения о реализации схемы сообщений для классов шаблонов см. [как: Создание виртуальной схемы сообщений для класса шаблона](../how-to-create-a-message-map-for-a-template-class.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="declare_message_map"></a>  DECLARE_MESSAGE_MAP

Объявляет, что класс определяет схему сообщений. Каждый `CCmdTarget`-производного класса в приложении необходимо указать схему сообщений для обработки сообщений.

### <a name="syntax"></a>Синтаксис

```
DECLARE_MESSAGE_MAP( )
```

### <a name="remarks"></a>Примечания

Используйте declare_message_map-макрос в конце объявления класса. Затем в CPP-файле, который определяет функции-члены класса, используйте begin_message_map-макрос, макрос записи для каждого из функционирования обработчика сообщений, а также end_message_map-макрос.

> [!NOTE]
>  Если после DECLARE_MESSAGE_MAP объявления любого члена, необходимо указать новый тип доступа (**открытый**, **частного**, или **защищенные**) для них.

Дополнительные сведения о схемы сообщений и declare_message_map-макрос, см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).

### <a name="example"></a>Пример

```cpp
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
```

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="end_message_map"></a>  END_MESSAGE_MAP

Завершает определение схему сообщения.

### <a name="syntax"></a>Синтаксис

```
END_MESSAGE_MAP( )
```

### <a name="remarks"></a>Примечания

Дополнительные сведения о схемы сообщений и end_message_map-макрос, см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="on_command"></a>  ON_COMMAND

Этот макрос сопоставляет сообщения команды к функции-члену.

### <a name="syntax"></a>Синтаксис

```
ON_COMMAND( commandId, memberFxn )
```

### <a name="parameters"></a>Параметры

*Идентификатор команды*<br/>
Идентификатор команды.

*memberFxn*<br/>
Имя функции обработчика сообщений, с которым сопоставляется команды.

### <a name="remarks"></a>Примечания

Он указывает, какая функция будет обрабатывать сообщения из объекта пользовательского интерфейса команды, такие как меню или панели инструментов кнопки команды.

Когда целевой объект команды получает сообщение Windows WM_COMMAND с указанным Идентификатором, ON_COMMAND вызывает функцию-член `memberFxn` для обработки сообщения.

Используйте ON_COMMAND для сопоставления одной команды к функции-члену. Используйте [ON_COMMAND_RANGE](#on_command_range) для сопоставления диапазона идентификаторов команд один член функции. Только одна запись схемы сообщений может соответствовать заданному идентификатору команды. То есть нельзя сопоставить команду несколько обработчиков. Дополнительные сведения и примеры см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).

### <a name="example"></a>Пример

```cpp
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_command_ex"></a>  ON_COMMAND_EX

Расширенные функции-члена обработчика команд.

### <a name="syntax"></a>Синтаксис

```
ON_COMMAND_EX(commandId, memberFxn);
```

### <a name="parameters"></a>Параметры

*Идентификатор команды*<br/>
Идентификатор команды.

*memberFxn*<br/>
Имя функции обработчика сообщений, с которым сопоставляется команды.

### <a name="remarks"></a>Примечания

Расширенную форму обработчики сообщений команда доступна для сложных вариантов использования. On_command_ex-макрос используется для таких обработчиков сообщений и предоставляет надмножество [ON_COMMAND](message-map-macros-mfc.md#on_command) функциональные возможности. Функции-члены расширенного обработчика команд принимать один параметр, целое число без знака, содержащее идентификатор команды и возвращают Логическое значение. Возвращаемое значение должно быть значение TRUE указывает, что команда должен быть обработан; в противном случае маршрутизации продолжит другие целевые объекты команды.

Дополнительные сведения см. в разделе техническое Примечание [TN006: Схемы сообщений] tm006-сообщение maps.md).

### <a name="requirements"></a>Требования

Header file: afxmsg_.h

## <a name="on_control"></a>  ON_CONTROL

Указывает, какая функция будет обрабатывать сообщение пользовательского уведомления.

### <a name="syntax"></a>Синтаксис

```
ON_CONTROL( wNotifyCode, commandId, memberFxn )
```

### <a name="parameters"></a>Параметры

*wNotifyCode*<br/>
Код уведомления элемента управления.

*Идентификатор команды*<br/>
Идентификатор команды.

*memberFxn*<br/>
Имя функции обработчика сообщений, с которым сопоставляется команды.

### <a name="remarks"></a>Примечания

Уведомляющих сообщений элемента управления являются сообщения от элемента управления своему родительскому окну.

Должно быть ровно один оператор ON_CONTROL макрос в схему сообщений для каждого сообщения уведомлений элемента управления, должны быть сопоставлены с функцию обработчика сообщений.

Дополнительные сведения и примеры см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_message"></a>  ON_MESSAGE

Указывает, какая функция будет обрабатывать определяемое пользователем сообщение.

### <a name="syntax"></a>Синтаксис

```
ON_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>Параметры

*message*<br/>
Идентификатор сообщения.

*memberFxn*<br/>
Имя функции обработчика сообщений, с которым сопоставляется сообщение.

Тип функции должен быть `afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`.

### <a name="remarks"></a>Примечания

Определяемые пользователем сообщения, сообщения, которые не являются стандартные сообщения Windows WM_MESSAGE. При выборе идентификатор сообщения, необходимо использовать значения в пределах диапазона от WM_USER (0x0400) 0x7FFF или WM_APP (0x8000) для 0xBFFF. Дополнительные сведения о сообщении идентификаторов см. в разделе [WM_APP](/windows/desktop/winmsg/wm-app).

Должно быть ровно один оператор ON_MESSAGE макрос в схему сообщений для каждого сообщения в определяемых пользователем, должны быть сопоставлены с функцию обработчика сообщений.

> [!NOTE]
>  Помимо определяемых пользователем сообщений ON_MESSAGE обрабатывает менее распространенные сообщения Windows. Дополнительные сведения см. в разделе [схемы сообщений](../../mfc/tn006-message-maps.md).

Дополнительные сведения и примеры см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md) и [определяемые пользователем обработчики](user-defined-handlers.md)

### <a name="example"></a>Пример

```cpp
#define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd2, CWnd)
   ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()

// inside the class declaration
afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

LRESULT CMyWnd2::OnMyMessage(WPARAM wParam, LPARAM lParam)
{
   UNREFERENCED_PARAMETER(wParam);
   UNREFERENCED_PARAMETER(lParam);

   // Handle message here.

   return 0;
}
```

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_olecmd"></a>  ON_OLECMD

Перенаправляет команды через интерфейс диспетчеризации команд `IOleCommandTarget`.

### <a name="syntax"></a>Синтаксис

```
ON_OLECMD( pguid, olecmdid, commandId )
```

### <a name="parameters"></a>Параметры

*pguid*<br/>
Идентификатор группы команд, к которому относится команда. Используйте NULL для стандартной группы.

*olecmdid*<br/>
Идентификатор команды OLE.

*Идентификатор команды*<br/>
Идентификатор меню, панели инструментов идентификатор, ИД кнопки или других идентификатор ресурса или объекта, используя следующую команду.

### <a name="remarks"></a>Примечания

`IOleCommandTarget` позволяет контейнер для получения команд, поступающих в пользовательском интерфейсе DocObject, а контейнер для отправки те же команды (такие как New, Open, "Сохранить как" и печать в меню "файл"; и скопируйте, вставьте, отменить, и так далее, в меню "Правка") для DocObject.

`IOleCommandTarget` проще, чем OLE-автоматизации `IDispatch`. `IOleCommandTarget` полностью зависит от стандартный набор команд, редко имеют аргументы, и сведения о типе не участвует (безопасность типа позволяет уменьшить также аргументов командной строки). Если требуется для отправки команд с аргументами, использовать [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd).

`IOleCommandTarget` Команд стандартного меню с MFC в реализованы следующие макросы:

**ON_OLECMD_CLEARSELECTION( )**

Отправляет команду Изменить очистить. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`

**ON_OLECMD_COPY( )**

Отправляет команду Правка копии. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`

**ON_OLECMD_CUT( )**

Отправляет команду Изменить Вырезать. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`

**ON_OLECMD_NEW( )**

Отправляет команды создания файла. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`

**ON_OLECMD_OPEN)**

Отправляет команды открытия файла. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`

**ON_OLECMD_PAGESETUP( )**

Отправляет команду настройки файла страницы. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`

**ON_OLECMD_PASTE( )**

Отправляет команду Изменить вставки. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`

**ON_OLECMD_PASTESPECIAL( )**

Отправляет команду Специальная вставка. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`

**ON_OLECMD_PRINT( )**

Отправляет команды Печать файла. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`

**ON_OLECMD_PRINTPREVIEW( )**

Отправляет команду Предварительный просмотр печати файла. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`

**ON_OLECMD_REDO( )**

Отправляет команду Изменить повтора. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`

**ON_OLECMD_SAVE( )**

Отправляет команду сохранения файла. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`

**ON_OLECMD_SAVE_AS( )**

Отправляет команды Сохранить как файл. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`

**ON_OLECMD_SAVE_COPY_AS( )**

Отправляет файл сохранить копию как команду. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`

**ON_OLECMD_SELECTALL( )**

Отправляет команду Изменить выделить все. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`

**ON_OLECMD_UNDO( )**

Отправляет команды Отменить изменение. Реализованы в виде:

`ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`

### <a name="requirements"></a>Требования

**Заголовок:** afxdocob.h

## <a name="on_registered_message"></a>  ON_REGISTERED_MESSAGE

Windows `RegisterWindowMessage` функция используется для определения нового сообщения окна, гарантированно будет уникальным во всей системе.

### <a name="syntax"></a>Синтаксис

```
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )
```

### <a name="parameters"></a>Параметры

*nMessageVariable*<br/>
Переменная ID зарегистрированных сообщения окна.

*memberFxn*<br/>
Имя функции обработчика сообщений, с которым сопоставляется сообщение.

### <a name="remarks"></a>Примечания

Этот макрос указывает, какая функция будет обрабатывать зарегистрированных сообщений.

Дополнительные сведения и примеры см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).

### <a name="example"></a>Пример

```cpp
static UINT NEAR WM_FIND = RegisterWindowMessage(_T("COMMDLG_FIND"));

BEGIN_MESSAGE_MAP(CMyWnd3, CWnd)
   ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_registered_thread_message"></a>  ON_REGISTERED_THREAD_MESSAGE

Указывает, какая функция будет обрабатывать сообщения, зарегистрированные с помощью функции Windows RegisterWindowMessage.

### <a name="syntax"></a>Синтаксис

```
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )
```

### <a name="parameters"></a>Параметры

*nMessageVariable*<br/>
Переменная ID зарегистрированных сообщения окна.

*memberFxn*<br/>
Имя функции обработчика CWinThread сообщений, с которым сопоставляется сообщение.

### <a name="remarks"></a>Примечания

RegisterWindowMessage используется для определения нового сообщения окна, гарантированно будет уникальным во всей системе. ON_REGISTERED_THREAD_MESSAGE должен использоваться вместо ON_REGISTERED_MESSAGE, при наличии CWinThread-класс.

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_thread_message"></a>  ON_THREAD_MESSAGE

Указывает, какая функция будет обрабатывать определяемое пользователем сообщение.

### <a name="syntax"></a>Синтаксис

```
ON_THREAD_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>Параметры

*message*<br/>
Идентификатор сообщения.

*memberFxn*<br/>
Имя `CWinThread`-сообщение-функция обработчика, с которым сопоставляется сообщение.

### <a name="remarks"></a>Примечания

При наличии необходимо использовать вместо ON_MESSAGE ON_THREAD_MESSAGE `CWinThread` класса. Определяемые пользователем сообщения, сообщения, которые не являются стандартные сообщения Windows WM_MESSAGE. Должно быть ровно один оператор ON_THREAD_MESSAGE макрос в схему сообщений для каждого сообщения в определяемых пользователем, должны быть сопоставлены с функцию обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="on_update_command_ui"></a>  ON_UPDATE_COMMAND_UI

Этот макрос указывает, какая функция будет обрабатывать сообщения команды обновления пользовательского интерфейса.

### <a name="syntax"></a>Синтаксис

```
ON_UPDATE_COMMAND_UI( messageId, memberFxn )
```

### <a name="parameters"></a>Параметры

*messageId*<br/>
Идентификатор сообщения.

*memberFxn*<br/>
Имя функции обработчика сообщений, с которым сопоставляется сообщение.

### <a name="remarks"></a>Примечания

Должно быть ровно один оператор макрос ON_UPDATE_COMMAND_UI в схему сообщений для каждой команды обновления пользовательского интерфейса, который должна быть сопоставлена с функцию обработчика сообщений.

Дополнительные сведения и примеры см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="on_command_range"></a>  ON_COMMAND_RANGE

Используйте этот макрос для сопоставления непрерывный диапазон идентификаторов, функция-обработчик одно сообщение.

### <a name="syntax"></a>Синтаксис

```
ON_COMMAND_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>Параметры

*id1*<br/>
Идентификатор команды в начале непрерывный диапазон идентификаторов команд.

*id2*<br/>
Идентификатор команды в конце непрерывный диапазон идентификаторов команд.

*memberFxn*<br/>
Имя функции обработчика сообщений, с которой сопоставлены команды.

### <a name="remarks"></a>Примечания

Диапазон идентификаторов начинается с *id1* и заканчивается *id2*.

Использование ON_COMMAND_RANGE для сопоставления диапазона идентификаторов команд один член функции. Используйте [ON_COMMAND](#on_command) для сопоставления одной команды к функции-члену. Только одна запись схемы сообщений может соответствовать заданному идентификатору команды. То есть нельзя сопоставить команду несколько обработчиков. Дополнительные сведения о диапазоны сопоставления сообщений, см. в разделе [обработчики для диапазонов схем сообщений](../../mfc/handlers-for-message-map-ranges.md).

Не поддерживается автоматическое для диапазонов схем сообщений, поэтому необходимо поместить макрос самостоятельно.

### <a name="example"></a>Пример

```cpp
// The code fragment below shows how to use ON_COMMAND_RANGE macro
// to map a contiguous range of command IDs to a single message
// handler function (i.e. OnRangeCmds() in the sample below). In
// addition, it also shows how to use CheckMenuRadioItem() to check a
// selected menu item and makes it a radio item.

BEGIN_MESSAGE_MAP(CChildFrame, CMDIChildWnd)
   ON_COMMAND_RANGE(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, &CChildFrame::OnRangeCmds)
END_MESSAGE_MAP()

void CChildFrame::OnRangeCmds(UINT nID)
{
   CMenu* mmenu = AfxGetMainWnd()->GetMenu();
   CMenu* submenu = mmenu->GetSubMenu(5);
   submenu->CheckMenuRadioItem(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3,
      nID, MF_BYCOMMAND);
}
```

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_update_command_ui_range"></a>  ON_UPDATE_COMMAND_UI_RANGE

Сопоставляется функции обработчика сообщений в одно обновление непрерывный диапазон идентификаторов команд.

### <a name="syntax"></a>Синтаксис

```
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>Параметры

*id1*<br/>
Идентификатор команды в начале непрерывный диапазон идентификаторов команд.

*id2*<br/>
Идентификатор команды в конце непрерывный диапазон идентификаторов команд.

*memberFxn*<br/>
Имя функции обработчика сообщений обновления, с которой сопоставлены команды.

### <a name="remarks"></a>Примечания

Обработчики сообщений обновления обновление состояния элементов меню и кнопки панели инструментов, связанный с данной командой. Диапазон идентификаторов начинается с *id1* и заканчивается *id2*.

Не поддерживается автоматическое для диапазонов схем сообщений, поэтому необходимо поместить макрос самостоятельно.

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_control_range"></a>  ON_CONTROL_RANGE

Используйте этот макрос для сопоставления функции обработчика одно сообщение для указанного сообщения уведомлений Windows, например BN_CLICKED непрерывный диапазон идентификаторов элементов управления.

### <a name="syntax"></a>Синтаксис

```
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )
```

### <a name="parameters"></a>Параметры

*wNotifyCode*<br/>
Код уведомления, к которой отвечает Ваш обработчик.

*id1*<br/>
Идентификатор команды в начале непрерывный диапазон идентификаторов элементов управления.

*id2*<br/>
Идентификатор команды в конце непрерывный диапазон идентификаторов элементов управления.

*memberFxn*<br/>
Имя функции обработчика сообщений, с которой сопоставляются элементы управления.

### <a name="remarks"></a>Примечания

Диапазон идентификаторов начинается с *id1* и заканчивается *id2*. Обработчик вызывается для указанного уведомления, поступающие от сопоставленные элементы управления.

Не поддерживается автоматическое для диапазонов схем сообщений, поэтому необходимо поместить макрос самостоятельно.

Дополнительные сведения о реализации функции обработчика для диапазона идентификаторов элементов управления см. [обработчики для диапазонов схем сообщений](../../mfc/handlers-for-message-map-ranges.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="see-also"></a>См. также

[ON_COMMAND](message-map-macros-mfc.md#on_command)<br/>
[TN006: Схемы сообщений](../tn006-message-maps.md)<br/>
[Класс COleCmdUI](colecmdui-class.md)<br/>
[COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)<br/>
[RegisterWindowMessage](/windows/desktop/api/winuser/nf-winuser-registerwindowmessagea)<br/>
[Пользовательские обработчики](user-defined-handlers.md)<br/>
[Класс CCmdUI](ccmdui-class.md)
