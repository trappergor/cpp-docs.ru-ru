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
ms.openlocfilehash: 6e9291f0f39057403bc27c7fe4ff5ca5a82dfe3a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356586"
---
# <a name="message-map-macros-mfc"></a>Макросы схемы сообщений (MFC)

Для поддержки карт сообщений MFC предоставляет следующие макросы:

### <a name="message-map-declaration-and-demarcation-macros"></a>Декларация сообщений-Карта и макрос ы демаркации

|||
|-|-|
|[DECLARE_MESSAGE_MAP](#declare_message_map)|Объявляет, что карта сообщений будет использоваться в классе для картирования сообщений к функциям (должна использоваться в декларации класса).|
|[BEGIN_MESSAGE_MAP](#begin_message_map)|Начинается определение карты сообщений (должно использоваться в реализации класса).|
|[BEGIN_TEMPLATE_MESSAGE_MAP](#begin_template_message_map)|Начинается определение карты сообщений на типе класса, содержащем один аргумент шаблона. |
|[END_MESSAGE_MAP](#end_message_map)|Завершает определение карты сообщений (должно использоваться в реализации класса).|

### <a name="message-mapping-macros"></a>Макрос ы сообщения-Картирование

|||
|-|-|
|[ON_COMMAND](#on_command)|Указывается, какая функция будет обрабатывать указанное командное сообщение.|
|[ON_COMMAND_EX](#on_command_ex)|Указывается, какая функция будет обрабатывать указанное командное сообщение.|
|[ON_CONTROL](#on_control)|Указывает, какая функция будет обрабатывать указанное сообщение о уведомлении управления.|
|[ON_MESSAGE](#on_message)|Указывает, какая функция будет обрабатывать сообщение, определяемое пользователем.|
|[ON_OLECMD](#on_olecmd)|Указывается, какая функция будет обрабатывать команду меню из DocObject или его контейнера.|
|[ON_REGISTERED_MESSAGE](#on_registered_message)|Указывает, какая функция будет обрабатывать зарегистрированное сообщение, определяемое пользователем.|
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|Указывает, какая функция будет обрабатывать зарегистрированное `CWinThread` сообщение с определенным пользователем, когда у вас есть класс.|
|[ON_THREAD_MESSAGE](#on_thread_message)|Указывает, какая функция будет обрабатывать пользовательское `CWinThread` сообщение, когда у вас есть класс.|
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|Указывает, какая функция будет обрабатывать определенное сообщение команды обновления пользовательского интерфейса.|

### <a name="message-map-range-macros"></a>Сообщение-Карта Диапазон Макрос

|||
|-|-|
|[ON_COMMAND_RANGE](#on_command_range)|Указывает, какая функция будет обрабатывать диапазон идовинов команд, указанных в первых двух параметрах макроса.|
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|Указывает, какой обработчик обновления будет обрабатывать диапазон идовинов команд, указанных в первых двух параметрах макроса.|
|[ON_CONTROL_RANGE](#on_control_range)|Указывает, какая функция будет обрабатывать уведомления из диапазона идентионное идентиматизм управления, указанного во втором и третьем параметрах, на макрос. Первым параметром является сообщение о контроле-уведомлении, например BN_CLICKED.|

Для получения дополнительной информации о картах сообщений, объявления хавки и макросах [Message Handling and Mapping Topics](../../mfc/message-handling-and-mapping.md)демаркации, а также макросах для отображения сообщений [см.](../../mfc/reference/message-maps-mfc.md) Для получения дополнительной информации о [Handlers for Message-Map Ranges](../../mfc/handlers-for-message-map-ranges.md)диапазонах сообщений-карты см.

## <a name="begin_message_map"></a><a name="begin_message_map"></a>BEGIN_MESSAGE_MAP

Начинается определение карты сообщений.

### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_MESSAGE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Упоняет название класса, на карте сообщений которого это.

*базовыйКласс*<br/>
Упогоняет название базового класса *Класса*.

### <a name="remarks"></a>Remarks

В файле реализации (.cpp), определяющем функции участника для вашего класса, запустите карту сообщений с BEGIN_MESSAGE_MAP макросом, затем добавьте макрозаписи для каждой из функций обработчика сообщений и заполните карту сообщений с помощью END_MESSAGE_MAP макроса.

Для получения дополнительной информации о картах сообщений см. [Карты сообщений](message-maps-mfc.md)

### <a name="example"></a>Пример

```cpp
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="begin_template_message_map"></a><a name="begin_template_message_map"></a>BEGIN_TEMPLATE_MESSAGE_MAP

Начинается определение карты сообщений на типе класса, содержащем один аргумент шаблона.

### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_TEMPLATE_MESSAGE_MAP( theClass, type_name, baseClass )
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Упоняет название класса, на карте сообщений которого это.

*type_name*<br/>
Имя параметра шаблона, указанного для класса.

*базовыйКласс*<br/>
Упогоняет название базового класса *Класса*.

### <a name="remarks"></a>Remarks

Этот макрос похож на [BEGIN_MESSAGE_MAP](message-map-macros-mfc.md#begin_message_map) макрос; однако этот макрос предназначен для классов, содержащих один аргумент шаблона.

В разделе реализации метода вашего класса запустите карту сообщений с BEGIN_TEMPLATE_MESSAGE_MAP макросом; затем добавьте макрозаписи для каждого из ваших методов обработчика сообщений, как и для стандартной карты сообщений. Как и в BEGIN_MESSAGE_MAP макросе, завершите карту сообщения шаблона с [END_MESSAGE_MAP](message-map-macros-mfc.md#end_message_map) макросом.

Для получения дополнительной информации о реализации карт сообщений для классов шаблонов, [обратитесь к Как: Создать карту сообщений для класса шаблонов](../how-to-create-a-message-map-for-a-template-class.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="declare_message_map"></a><a name="declare_message_map"></a>DECLARE_MESSAGE_MAP

Объявляет, что класс определяет карту сообщений. Каждый `CCmdTarget`класс, полученный в вашей программе, должен предоставить карту сообщений для обработки сообщений.

### <a name="syntax"></a>Синтаксис

```cpp
DECLARE_MESSAGE_MAP( )
```

### <a name="remarks"></a>Remarks

Используйте DECLARE_MESSAGE_MAP макрос в конце объявления класса. Затем в файле .cpp, который определяет функции участника для класса, используйте BEGIN_MESSAGE_MAP макрозаписи, макрозаписи для каждой из функций обработчика сообщений, а также END_MESSAGE_MAP макрос.

> [!NOTE]
> Если вы объявляете какой-либо участник после DECLARE_MESSAGE_MAP, вы должны указать новый тип доступа **(государственный,** **частный**или **защищенный)** для них.

Для получения дополнительной информации о [картах](../../mfc/message-handling-and-mapping.md)сообщений и DECLARE_MESSAGE_MAP макросе, см.

### <a name="example"></a>Пример

```cpp
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
```

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="end_message_map"></a><a name="end_message_map"></a>END_MESSAGE_MAP

Завершает определение карты сообщений.

### <a name="syntax"></a>Синтаксис

```cpp
END_MESSAGE_MAP( )
```

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о [картах](../../mfc/message-handling-and-mapping.md)сообщений и END_MESSAGE_MAP макросе см.

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="on_command"></a><a name="on_command"></a>ON_COMMAND

Этот макрос отображает командное сообщение функции участника.

### <a name="syntax"></a>Синтаксис

```cpp
ON_COMMAND( commandId, memberFxn )
```

### <a name="parameters"></a>Параметры

*commandId*<br/>
Идентификатор команды.

*memberFxn*<br/>
Имя функции обработчика сообщений, к которой отображается команда.

### <a name="remarks"></a>Remarks

Он указывает, какая функция будет обрабатывать командное сообщение от объекта пользовательского интерфейса команды, такого как элемент меню или кнопка панели инструментов.

Когда объект командной цели получает сообщение WM_COMMAND Windows с указанным `memberFxn` идентификатором, ON_COMMAND вызовут функцию участника для обработки сообщения.

Используйте ON_COMMAND для отображения одной команды с функцией члена. Используйте [ON_COMMAND_RANGE](#on_command_range) для картирования ряда идонов команд на одну функцию. Только один вход на карту сообщений может соответствовать заданной идентификатору команды. То есть, вы не можете сопоставить команду с более чем одним обработчиком. Для получения дополнительной информации и [примеров см.](../../mfc/message-handling-and-mapping.md)

### <a name="example"></a>Пример

```cpp
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_command_ex"></a><a name="on_command_ex"></a>ON_COMMAND_EX

Расширенная функция обработчика команд.

### <a name="syntax"></a>Синтаксис

```cpp
ON_COMMAND_EX(commandId, memberFxn);
```

### <a name="parameters"></a>Параметры

*commandId*<br/>
Идентификатор команды.

*memberFxn*<br/>
Имя функции обработчика сообщений, к которой отображается команда.

### <a name="remarks"></a>Remarks

Расширенная форма обработчиков командных сообщений доступна для расширенного использования. Для таких обработчиков сообщений используется ON_COMMAND_EX макрос, который обеспечивает сверхнабор [ON_COMMAND](message-map-macros-mfc.md#on_command) функциональности. Расширенные функции обработчика команд принимают один параметр, UINT, содержащий идентификатор команды, и возвращают BOOL. Значение возврата должно быть правдой, чтобы указать, что команда была обработана; в противном случае реаутирование будет продолжено к другим объектам цели команды.

Для получения дополнительной информации см. Техническое примечание «TN006: Карты сообщений» tm006-сообщение-maps.md).

### <a name="requirements"></a>Требования

Файл заголовка: afxmsg_.h

## <a name="on_control"></a><a name="on_control"></a>ON_CONTROL

Указывает, какая функция будет обрабатывать сообщение уведомления пользовательского управления.

### <a name="syntax"></a>Синтаксис

```cpp
ON_CONTROL( wNotifyCode, commandId, memberFxn )
```

### <a name="parameters"></a>Параметры

*wNotifyCode*<br/>
Код уведомления элемента управления.

*commandId*<br/>
Идентификатор команды.

*memberFxn*<br/>
Имя функции обработчика сообщений, к которой отображается команда.

### <a name="remarks"></a>Remarks

Сообщения уведомления управления — это сообщения, отправляемые из элемента управления в родительское окно.

На карте сообщений должно быть ровно одно ON_CONTROL макроса для каждого сообщения о уведомлении управления, которое должно быть отображено к функции обработчика сообщений.

Для получения дополнительной информации и [примеров см.](../../mfc/message-handling-and-mapping.md)

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_message"></a><a name="on_message"></a>ON_MESSAGE

Указывает, какая функция будет обрабатывать сообщение, определяемое пользователем.

### <a name="syntax"></a>Синтаксис

```cpp
ON_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>Параметры

*Сообщение*<br/>
Идентификатор сообщения.

*memberFxn*<br/>
Имя функции обработчика сообщений, к которой отображается сообщение.

Тип функции должен `afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`быть.

### <a name="remarks"></a>Remarks

Сообщения, определяемые пользователем, — это любые сообщения, которые не являются стандартными WM_MESSAGE сообщений Windows. При выборе идентификатора сообщения необходимо использовать значения в пределах WM_USER (0x0400) до 0x7FFF или WM_APP (0x8000) до 0xBFFF. Для получения дополнительной информации об ипотированных сообщениях [WM_APP](/windows/win32/winmsg/wm-app)см.

На карте сообщений должно быть ровно один ON_MESSAGE макросом для каждого сообщения, определяемого пользователем, которое должно быть отображено к функции обработчика сообщений.

> [!NOTE]
> Помимо сообщений, определяемых пользователем, ON_MESSAGE обрабатывает менее распространенные сообщения Windows. Для получения дополнительной информации смотрите [Карты сообщений](../../mfc/tn006-message-maps.md).

Для получения дополнительной информации и примеров [см.](../../mfc/message-handling-and-mapping.md) [User-Defined Handlers](user-defined-handlers.md)

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

## <a name="on_olecmd"></a><a name="on_olecmd"></a>ON_OLECMD

Маршруты командчерез интерфейс `IOleCommandTarget`диспетчерской команды.

### <a name="syntax"></a>Синтаксис

```cpp
ON_OLECMD( pguid, olecmdid, commandId )
```

### <a name="parameters"></a>Параметры

*pguid*<br/>
Идентификация командной группы, к которой принадлежит команда. Используйте NULL для стандартной группы.

*олекмдид*<br/>
Идентификатор команды OLE.

*commandId*<br/>
Идентификатор меню, идентификатор панели инструментов, идентификатор кнопки или другой идентификатор ресурса или объекта, выдающий команду.

### <a name="remarks"></a>Remarks

`IOleCommandTarget`позволяет контейнеру получать команды, которые возникают в пользовательском интерфейсе DocObject, и позволяет контейнеру отправлять те же команды (такие как New, Open, SaveAs и Печать в меню файла; и Копировать, вставить, отменить и так далее в меню Edit) в DocObject.

`IOleCommandTarget`проще, чем у `IDispatch`OLE Automation. `IOleCommandTarget`полностью опирается на стандартный набор команд, которые редко имеют аргументы, и не тип информации участвует (тип безопасности уменьшается для командных аргументов, а). Если вам нужно отправить команды с аргументами, используйте [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd).

Стандартные `IOleCommandTarget` команды меню были реализованы MFC в следующих макросах:

**ON_OLECMD_CLEARSELECTION()**

Отправляет команду Edit Clear. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`

**ON_OLECMD_COPY()**

Отправляет команду Edit Copy. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`

**ON_OLECMD_CUT()**

Отправляет команду Edit Cut. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`

**ON_OLECMD_NEW()**

Отправляет новую команду файла. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`

**ON_OLECMD_OPEN()**

Отправляет команду File Open. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`

**ON_OLECMD_PAGESETUP()**

Отправляет команду настройки страницы файлов. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`

**ON_OLECMD_PASTE()**

Отправляет команду Edit Paste. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`

**ON_OLECMD_PASTESPECIAL()**

Отправляет специальную команду Edit Paste. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`

**ON_OLECMD_PRINT()**

Отправляет команду печати файлов. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`

**ON_OLECMD_PRINTPREVIEW()**

Отправляет команду предварительного просмотра типографии файла. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`

**ON_OLECMD_REDO()**

Отправляет команду Edit Redo. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`

**ON_OLECMD_SAVE()**

Отправляет команду сохранения файлов. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`

**ON_OLECMD_SAVE_AS()**

Отправляет файл Сохранить как команду. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`

**ON_OLECMD_SAVE_COPY_AS()**

Отправляет файл Сохранить копию как команду. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`

**ON_OLECMD_SELECTALL()**

Отправляет команду Edit Select All. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`

**ON_OLECMD_UNDO()**

Отправляет команду Edit Undo. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`

### <a name="requirements"></a>Требования

**Заголовок:** afxdocob.h

## <a name="on_registered_message"></a><a name="on_registered_message"></a>ON_REGISTERED_MESSAGE

Функция `RegisterWindowMessage` Windows используется для определения нового сообщения окна, которое гарантированно будет уникальным во всей системе.

### <a name="syntax"></a>Синтаксис

```cpp
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )
```

### <a name="parameters"></a>Параметры

*nMessageПеременный*<br/>
Зарегистрированная переменная идентификатора оконного сообщения.

*memberFxn*<br/>
Имя функции обработчика сообщений, к которой отображается сообщение.

### <a name="remarks"></a>Remarks

Этот макрос указывает, какая функция будет обрабатывать зарегистрированное сообщение.

Для получения дополнительной информации и [примеров см.](../../mfc/message-handling-and-mapping.md)

### <a name="example"></a>Пример

```cpp
static UINT NEAR WM_FIND = RegisterWindowMessage(_T("COMMDLG_FIND"));

BEGIN_MESSAGE_MAP(CMyWnd3, CWnd)
   ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_registered_thread_message"></a><a name="on_registered_thread_message"></a>ON_REGISTERED_THREAD_MESSAGE

Указывает, какая функция будет обрабатывать сообщение, зарегистрированное функцией Windows RegisterWindowMessage.

### <a name="syntax"></a>Синтаксис

```cpp
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )
```

### <a name="parameters"></a>Параметры

*nMessageПеременный*<br/>
Зарегистрированная переменная идентификатора оконного сообщения.

*memberFxn*<br/>
Название функции CWinThread-сообщение-обработчик, к которому отображается сообщение.

### <a name="remarks"></a>Remarks

RegisterWindowMessage используется для определения нового сообщения окна, которое гарантированно будет уникальным во всей системе. ON_REGISTERED_THREAD_MESSAGE должны использоваться вместо ON_REGISTERED_MESSAGE, когда у вас есть класс CWinThread.

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_thread_message"></a><a name="on_thread_message"></a>ON_THREAD_MESSAGE

Указывает, какая функция будет обрабатывать сообщение, определяемое пользователем.

### <a name="syntax"></a>Синтаксис

```cpp
ON_THREAD_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>Параметры

*Сообщение*<br/>
Идентификатор сообщения.

*memberFxn*<br/>
Имя функции `CWinThread`-сообщение-обработчик, к которой отображается сообщение.

### <a name="remarks"></a>Remarks

ON_THREAD_MESSAGE должны использоваться, а не `CWinThread` ON_MESSAGE, когда у вас есть класс. Сообщения, определяемые пользователем, — это любые сообщения, которые не являются стандартными WM_MESSAGE сообщений Windows. На карте сообщений должно быть ровно одно ON_THREAD_MESSAGE макроса для каждого сообщения, определяемого пользователем, которое должно быть отображено к функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="on_update_command_ui"></a><a name="on_update_command_ui"></a>On_update_command_ui

Этот макрос указывает, какая функция будет обрабатывать сообщение команды обновления пользовательского интерфейса.

### <a name="syntax"></a>Синтаксис

```cpp
ON_UPDATE_COMMAND_UI( messageId, memberFxn )
```

### <a name="parameters"></a>Параметры

*Messageid*<br/>
Идентификатор сообщения.

*memberFxn*<br/>
Имя функции обработчика сообщений, к которой отображается сообщение.

### <a name="remarks"></a>Remarks

На карте сообщений должно быть ровно один ON_UPDATE_COMMAND_UI макросом для каждой команды обновления пользовательского интерфейса, которая должна быть отображана с функцией обработчика сообщений.

Для получения дополнительной информации и [примеров см.](../../mfc/message-handling-and-mapping.md)

### <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="on_command_range"></a><a name="on_command_range"></a>ON_COMMAND_RANGE

Используйте этот макрос для отображения смежного диапазона идонов команд в одну функцию обработчика сообщений.

### <a name="syntax"></a>Синтаксис

```cpp
ON_COMMAND_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>Параметры

*id1*<br/>
Идентификатор командования в начале смежного диапазона идентификаторов командования.

*id2*<br/>
Идентификатор командования в конце смежного диапазона идентификаторов команд.

*memberFxn*<br/>
Имя функции обработчика сообщений, к которой отображаются команды.

### <a name="remarks"></a>Remarks

Диапазон идентификаторов начинается с *id1* и заканчивается *id2*.

Используйте ON_COMMAND_RANGE для картирования ряда идонов команд на одну функцию. Используйте [ON_COMMAND](#on_command) для отображения одной команды с функцией члена. Только один вход на карту сообщений может соответствовать заданной идентификатору команды. То есть, вы не можете сопоставить команду с более чем одним обработчиком. Для получения дополнительной информации о [Handlers for Message-Map Ranges](../../mfc/handlers-for-message-map-ranges.md)диапазонах отображения сообщений см.

Автоматической поддержки диапазонов карт сообщений не существует, поэтому необходимо разместить макрос самостоятельно.

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

## <a name="on_update_command_ui_range"></a><a name="on_update_command_ui_range"></a>ON_UPDATE_COMMAND_UI_RANGE

Отображает смежный диапазон идонов команд к одной функции обработчика сообщений обновления.

### <a name="syntax"></a>Синтаксис

```cpp
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>Параметры

*id1*<br/>
Идентификатор командования в начале смежного диапазона идентификаторов командования.

*id2*<br/>
Идентификатор командования в конце смежного диапазона идентификаторов команд.

*memberFxn*<br/>
Название функции обработчика сообщений обновления, к которой отображаются команды.

### <a name="remarks"></a>Remarks

Обработчики сообщений обновления обновляют состояние элементов меню и кнопок панели инструментов, связанных с командой. Диапазон идентификаторов начинается с *id1* и заканчивается *id2*.

Автоматической поддержки диапазонов карт сообщений не существует, поэтому необходимо разместить макрос самостоятельно.

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_control_range"></a><a name="on_control_range"></a>ON_CONTROL_RANGE

Используйте этот макрос для отображения смежного диапазона иик-идов управления с одной функцией обработчика сообщений для определенного сообщения уведомлений Windows, например BN_CLICKED.

### <a name="syntax"></a>Синтаксис

```cpp
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )
```

### <a name="parameters"></a>Параметры

*wNotifyCode*<br/>
Код уведомления, на который отвечает ваш обработчик.

*id1*<br/>
Идентификатор командования в начале смежного диапазона идентификаторов управления.

*id2*<br/>
Идентификатор командования в конце смежного диапазона идентификаторов управления.

*memberFxn*<br/>
Имя функции обработчика сообщений, к которой отображаются элементы управления.

### <a name="remarks"></a>Remarks

Диапазон идентификаторов начинается с *id1* и заканчивается *id2*. Обработчик вызывается для указанного уведомления, поступающего от любого из отображеных элементов управления.

Автоматической поддержки диапазонов карт сообщений не существует, поэтому необходимо разместить макрос самостоятельно.

Для получения дополнительной информации о функциях обработчика для ряда идонов управления обратитесь к [обработчикам для диапазонов сообщений и карт.](../../mfc/handlers-for-message-map-ranges.md)

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="see-also"></a>См. также раздел

[ON_COMMAND](message-map-macros-mfc.md#on_command)<br/>
[TN006. Схемы сообщений](../tn006-message-maps.md)<br/>
[Класс COleCmdUI](colecmdui-class.md)<br/>
[ColeServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)<br/>
[RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew)<br/>
[Обработчики, определяемые пользователем](user-defined-handlers.md)<br/>
[Класс CCmdUI](ccmdui-class.md)
