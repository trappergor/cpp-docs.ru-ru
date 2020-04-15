---
title: Класс COleDataSource
ms.date: 11/04/2016
f1_keywords:
- COleDataSource
- AFXOLE/COleDataSource
- AFXOLE/COleDataSource::COleDataSource
- AFXOLE/COleDataSource::CacheData
- AFXOLE/COleDataSource::CacheGlobalData
- AFXOLE/COleDataSource::DelayRenderData
- AFXOLE/COleDataSource::DelayRenderFileData
- AFXOLE/COleDataSource::DelaySetData
- AFXOLE/COleDataSource::DoDragDrop
- AFXOLE/COleDataSource::Empty
- AFXOLE/COleDataSource::FlushClipboard
- AFXOLE/COleDataSource::GetClipboardOwner
- AFXOLE/COleDataSource::OnRenderData
- AFXOLE/COleDataSource::OnRenderFileData
- AFXOLE/COleDataSource::OnRenderGlobalData
- AFXOLE/COleDataSource::OnSetData
- AFXOLE/COleDataSource::SetClipboard
helpviewer_keywords:
- COleDataSource [MFC], COleDataSource
- COleDataSource [MFC], CacheData
- COleDataSource [MFC], CacheGlobalData
- COleDataSource [MFC], DelayRenderData
- COleDataSource [MFC], DelayRenderFileData
- COleDataSource [MFC], DelaySetData
- COleDataSource [MFC], DoDragDrop
- COleDataSource [MFC], Empty
- COleDataSource [MFC], FlushClipboard
- COleDataSource [MFC], GetClipboardOwner
- COleDataSource [MFC], OnRenderData
- COleDataSource [MFC], OnRenderFileData
- COleDataSource [MFC], OnRenderGlobalData
- COleDataSource [MFC], OnSetData
- COleDataSource [MFC], SetClipboard
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
ms.openlocfilehash: fcf9505a7792aea6807e37f05cd1cb1aaad55830
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366122"
---
# <a name="coledatasource-class"></a>Класс COleDataSource

Играет роль кэша, в который приложение помещает данные, которые оно будет предлагать во время операций передачи данных, таких как операции с буфером обмена или операции перетаскивания.

## <a name="syntax"></a>Синтаксис

```
class COleDataSource : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeDataИсточник::COleDataИсточник](#coledatasource)|Формирует объект `COleDataSource`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleDataИсточник::CacheData](#cachedata)|Предложения данных в определенном формате с использованием `STGMEDIUM` структуры.|
|[COleDataИсточник::CacheGlobalData](#cacheglobaldata)|Предложения данных в определенном формате с помощью HGLOBAL.|
|[ColeDataИсточник::DelayRenderData](#delayrenderdata)|Предложения данных в определенном формате с использованием задержки рендеринга.|
|[ColeDataИсточник::DelayRenderFileData](#delayrenderfiledata)|Предложения данных в указанном формате в `CFile` указателе.|
|[ColeDataИсточник::DelaySetData](#delaysetdata)|Вызывается для каждого формата, который поддерживается в `OnSetData`.|
|[ColeDataИсточник::DoDragDrop](#dodragdrop)|Выполняет операции перетаскивания с помощью источника данных.|
|[ColeDataИсточник::Пустой](#empty)|Опустошает `COleDataSource` объект данных.|
|[ColeDataИсточник::FlushClipboard](#flushclipboard)|Переиздавив все данные в Clipboard.|
|[ColeDataИсточник::GetClipboardВладелец](#getclipboardowner)|Проверяет, что данные, размещенные на Clipboard все еще там.|
|[ColeDataИсточник::OnRenderData](#onrenderdata)|Извлекает данные в рамках задержки рендеринга.|
|[ColeDataИсточник::OnrenderFileData](#onrenderfiledata)|Извлекает данные `CFile` в часть задержки рендеринга.|
|[ColeDataИсточник::OnrenderGlobalData](#onrenderglobaldata)|Извлекает данные в HGLOBAL в рамках задержки рендеринга.|
|[ColeDataИсточник::OnsetData](#onsetdata)|Вызывается для замены `COleDataSource` данных в объекте.|
|[ColeDataИсточник::SetClipboard](#setclipboard)|Разместите `COleDataSource` объект на clipboard.|

## <a name="remarks"></a>Remarks

Вы можете создавать источники данных OLE напрямую. Кроме того, классы [COleClientItem](../../mfc/reference/coleclientitem-class.md) и [COleServerItem](../../mfc/reference/coleserveritem-class.md) создают `CopyToClipboard` источники данных OLE в ответ на их и `DoDragDrop` функции членов. Смотрите [COleServerItem::CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard) для краткого описания. Переопределить `OnGetClipboardData` функцию участника вашего клиента элемента или класса элемента сервера, чтобы добавить `CopyToClipboard` `DoDragDrop` дополнительные форматы Clipboard к данным в источнике данных OLE, созданных для функции или члена.

Всякий раз, когда вы хотите подготовить данные для передачи, вы должны создать объект этого класса и заполнить его с вашими данными, используя наиболее подходящий метод для ваших данных. Способ вставки в источник данных непосредственно зависит от того, поставляются ли данные немедленно (немедленная визуализация) или по требованию (задержка рендеринга). Для каждого формата Clipboard, в котором вы предоставляете данные, передавая формат Clipboard для использования (и дополнительную структуру [FORMATETC),](/windows/win32/api/objidl/ns-objidl-formatetc) позвоните [в DelayRenderData.](#delayrenderdata)

Для получения дополнительной информации об источниках [Data Objects and Data Sources (OLE)](../../mfc/data-objects-and-data-sources-ole.md)данных и передаче данных см. Кроме того, в статье [Clipboard Topics](../../mfc/clipboard.md) описывается механизм OL Clipboard.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDataSource`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="coledatasourcecachedata"></a><a name="cachedata"></a>COleDataИсточник::CacheData

Назовите эту функцию, чтобы указать формат, в котором данные предлагаются во время операций передачи данных.

```
void CacheData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*cfFormat*<br/>
Формат Clipboard, в котором будут предлагаться данные. Этот параметр может быть одним из предопределенных форматов Clipboard или значением, возвращенным родной функцией Windows [RegisterClipboardFormat.](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)

*lpStgMedium*<br/>
Указывает на структуру [STGMEDIUM,](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) содержащую данные в указанном формате.

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC,](/windows/win32/api/objidl/ns-objidl-formatetc) описывающую формат, в котором будут предлагаться данные. Предоставьте значение для этого параметра, если вы хотите указать дополнительную информацию о формате за пределами формата Clipboard, указанного *cfFormat.* Если это NULL, значения по умолчанию используются `FORMATETC` для других полей в структуре.

### <a name="remarks"></a>Remarks

Вы должны предоставить данные, потому что эта функция обеспечивает его с помощью немедленного рендеринга. Данные кэшируется до необходимости.

Предоставируйте данные с помощью структуры [STGMEDIUM.](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) Вы также можете `CacheGlobalData` использовать функцию члена, если объем данных, которые вы поставляете, достаточно мал, чтобы быть переданы эффективно с помощью HGLOBAL.

После вызова `CacheData` к `ptd` члену `lpFormatEtc` и содержимое *lpStgMedium* принадлежат объекту данных, а не вызывающему.

Чтобы использовать задержку рендеринга, позвоните в функцию [участника DelayRenderData](#delayrenderdata) или [DelayRenderFileData.](#delayrenderfiledata) Для получения дополнительной информации о задержке рендеринга, обрабатываемых MFC, см. [Data Objects and Data Sources: Manipulation](../../mfc/data-objects-and-data-sources-manipulation.md)

Для получения дополнительной информации, см [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) и [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) структур в Windows SDK.

Для получения дополнительной информации, [см. RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

## <a name="coledatasourcecacheglobaldata"></a><a name="cacheglobaldata"></a>COleDataИсточник::CacheGlobalData

Назовите эту функцию, чтобы указать формат, в котором данные предлагаются во время операций передачи данных.

```
void CacheGlobalData(
    CLIPFORMAT cfFormat,
    HGLOBAL hGlobal,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*cfFormat*<br/>
Формат Clipboard, в котором будут предлагаться данные. Этот параметр может быть одним из предопределенных форматов Clipboard или значением, возвращенным родной функцией Windows [RegisterClipboardFormat.](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)

*Hglobal*<br/>
Обработка глобального блока памяти, содержащего данные в указанном формате.

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC,](/windows/win32/api/objidl/ns-objidl-formatetc) описывающую формат, в котором будут предлагаться данные. Предоставьте значение для этого параметра, если вы хотите указать дополнительную информацию о формате за пределами формата Clipboard, указанного *cfFormat.* Если это NULL, значения по умолчанию используются `FORMATETC` для других полей в структуре.

### <a name="remarks"></a>Remarks

Эта функция предоставляет данные с помощью немедленного рендеринга, поэтому при вызове функции необходимо предоставить данные; данные кэшируется до необходимости. Используйте `CacheData` функцию участника, если вы поставляете большой объем данных или если вам требуется структурированная среда хранения.

Чтобы использовать задержку рендеринга, позвоните в функцию [участника DelayRenderData](#delayrenderdata) или [DelayRenderFileData.](#delayrenderfiledata) Для получения дополнительной информации о задержке рендеринга, обрабатываемых MFC, см. [Data Objects and Data Sources: Manipulation](../../mfc/data-objects-and-data-sources-manipulation.md)

Для получения дополнительной [информации](/windows/win32/api/objidl/ns-objidl-formatetc) см.

Для получения дополнительной информации, [см. RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

## <a name="coledatasourcecoledatasource"></a><a name="coledatasource"></a>ColeDataИсточник::COleDataИсточник

Формирует объект `COleDataSource`.

```
COleDataSource();
```

## <a name="coledatasourcedelayrenderdata"></a><a name="delayrenderdata"></a>ColeDataИсточник::DelayRenderData

Назовите эту функцию, чтобы указать формат, в котором данные предлагаются во время операций передачи данных.

```
void DelayRenderData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*cfFormat*<br/>
Формат Clipboard, в котором будут предлагаться данные. Этот параметр может быть одним из предопределенных форматов Clipboard или значением, возвращенным родной функцией Windows [RegisterClipboardFormat.](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC,](/windows/win32/api/objidl/ns-objidl-formatetc) описывающую формат, в котором будут предлагаться данные. Предоставьте значение для этого параметра, если вы хотите указать дополнительную информацию о формате за пределами формата Clipboard, указанного *cfFormat.* Если это NULL, значения по умолчанию используются `FORMATETC` для других полей в структуре.

### <a name="remarks"></a>Remarks

Эта функция предоставляет данные с помощью задержки рендеринга, поэтому данные не поставляются немедленно. Функция участника [OnRenderData](#onrenderdata) или [OnRenderGlobalData](#onrenderglobaldata) называется для запроса данных.

Используйте эту функцию, если вы не `CFile` собираетесь поставлять данные через объект. Если вы собираетесь предоставить `CFile` данные через объект, позвоните в функцию участника [DelayRenderFileData.](#delayrenderfiledata) Для получения дополнительной информации о задержке рендеринга, обрабатываемых MFC, см. [Data Objects and Data Sources: Manipulation](../../mfc/data-objects-and-data-sources-manipulation.md)

Чтобы использовать немедленную визуализацию, позвоните в функцию члена [Кэш-Дата](#cachedata) или [КэшГлглбаза.](#cacheglobaldata)

Для получения дополнительной [информации](/windows/win32/api/objidl/ns-objidl-formatetc) см.

Для получения дополнительной информации, [см. RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

## <a name="coledatasourcedelayrenderfiledata"></a><a name="delayrenderfiledata"></a>ColeDataИсточник::DelayRenderFileData

Назовите эту функцию, чтобы указать формат, в котором данные предлагаются во время операций передачи данных.

```
void DelayRenderFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*cfFormat*<br/>
Формат Clipboard, в котором будут предлагаться данные. Этот параметр может быть одним из предопределенных форматов Clipboard или значением, возвращенным родной функцией Windows [RegisterClipboardFormat.](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC,](/windows/win32/api/objidl/ns-objidl-formatetc) описывающую формат, в котором будут предлагаться данные. Предоставьте значение для этого параметра, если вы хотите указать дополнительную информацию о формате за пределами формата Clipboard, указанного *cfFormat.* Если это NULL, значения по умолчанию используются `FORMATETC` для других полей в структуре.

### <a name="remarks"></a>Remarks

Эта функция предоставляет данные с помощью задержки рендеринга, поэтому данные не поставляются немедленно. Функция члена [OnRenderFileData](#onrenderfiledata) называется для запроса данных.

Используйте эту функцию, если `CFile` вы собираетесь использовать объект для передачи данных. Если вы не собираетесь `CFile` использовать объект, позвоните в функцию участника [DelayRenderData.](#delayrenderdata) Для получения дополнительной информации о задержке рендеринга, обрабатываемых MFC, см. [Data Objects and Data Sources: Manipulation](../../mfc/data-objects-and-data-sources-manipulation.md)

Чтобы использовать немедленную визуализацию, позвоните в функцию члена [Кэш-Дата](#cachedata) или [КэшГлглбаза.](#cacheglobaldata)

Для получения дополнительной [информации](/windows/win32/api/objidl/ns-objidl-formatetc) см.

Для получения дополнительной информации, [см. RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

## <a name="coledatasourcedelaysetdata"></a><a name="delaysetdata"></a>ColeDataИсточник::DelaySetData

Вызовите эту функцию для поддержки изменения содержимого источника данных.

```
void DelaySetData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Параметры

*cfFormat*<br/>
Формат Clipboard, в котором должны размещаться данные. Этот параметр может быть одним из предопределенных форматов Clipboard или значением, возвращенным родной функцией Windows [RegisterClipboardFormat.](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC,](/windows/win32/api/objidl/ns-objidl-formatetc) описывающую формат, в котором данные должны быть заменены. Предоставьте значение для этого параметра, если вы хотите указать дополнительную информацию о формате за пределами формата Clipboard, указанного *cfFormat.* Если это NULL, значения по умолчанию используются `FORMATETC` для других полей в структуре.

### <a name="remarks"></a>Remarks

[OnSetData](#onsetdata) будет вызываться в рамках, когда это произойдет. Это используется только тогда, когда фреймворк возвращает источник данных из [COleServerItem::GetDataSource](../../mfc/reference/coleserveritem-class.md#getdatasource). Если `DelaySetData` функция не `OnSetData` будет вызвана, ваша функция никогда не будет вызываться. `DelaySetData`должны быть вызваны для `FORMATETC` каждого Clipboard или формата вы поддерживаете.

Для получения дополнительной [информации](/windows/win32/api/objidl/ns-objidl-formatetc) см.

Для получения дополнительной информации, [см. RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) в Windows SDK.

## <a name="coledatasourcedodragdrop"></a><a name="dodragdrop"></a>ColeDataИсточник::DoDragDrop

Вызов `DoDragDrop` функции участника для выполнения операции перетаскивания для этого источника данных, как правило, в обработчике [CWnd:OnLButtonDown.](../../mfc/reference/cwnd-class.md#onlbuttondown)

```
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,
    LPCRECT lpRectStartDrag = NULL,
    COleDropSource* pDropSource = NULL);
```

### <a name="parameters"></a>Параметры

*dwEffects*<br/>
Операции перетаскивания и падения, разрешенные в этом источнике данных. Может быть один или несколько из следующих:

- DROPEFFECT_COPY может быть выполнена операция копирования.

- DROPEFFECT_MOVE операция перемещения может быть выполнена.

- DROPEFFECT_LINK можно установить связь с упавшими данными с исходными данными.

- DROPEFFECT_SCROLL указывает на то, что может произойти операция перетаскиваемого прокрутки.

*lpRectStartDrag*<br/>
Указатель на прямоугольник, который определяет, где на самом деле начинается сопротивление. Дополнительные сведения см. в разделе "Примечания".

*pDropSource*<br/>
Указывает на источник капли. Если NULL, то по умолчанию реализация [COleDropSource](../../mfc/reference/coledropsource-class.md) будет использоваться.

### <a name="return-value"></a>Возвращаемое значение

Эффект выпадения, генерируемый операцией перетаскивания; в противном случае DROPEFFECT_NONE если операция никогда не начинается, потому что пользователь выпустил кнопку мыши, прежде чем покинуть поставленный прямоугольник.

### <a name="remarks"></a>Remarks

Операция перетаскивания начинается не сразу. Он ждет, пока курсор мыши не покинет прямоугольник, указанный *lpRectStartDrag,* или до тех пор, пока не пройдет определенное количество миллисекунд. Если *lpRectStartDrag* является NULL, размер прямоугольника составляет один пиксель.

Время задержки определяется параметром ключа реестра. Вы можете изменить время задержки, позвонив [в CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) или [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Если вы не указали время задержки, используется значение по умолчанию 200 миллисекунд. Время задержки перетаскивания сохраняется следующим образом:

- Время задержки Windows NT Drag хранится в HKEY_LOCAL_MACHINE»SOFTWARE-Microsoft-Windows-NT-CurrentVersion-IniFileMapping-win.ini-Windows-DragDelay.

- Время задержки Windows 3.x Перетащите сохраняется в WIN. Файл INI, в разделе «Окна».

- Время задержки Windows 95/98 перетащите хранится в кэшированной версии WIN. Ini.

Для получения дополнительной информации о том, как информация о задержке перетаскивания хранится в реестре или . INI файл, [см. WriteProfileString](/windows/win32/api/winbase/nf-winbase-writeprofilestringw) в Windows SDK.

Для получения дополнительной информации, [см.](../../mfc/drag-and-drop-ole.md)

## <a name="coledatasourceempty"></a><a name="empty"></a>ColeDataИсточник::Пустой

Вызовите эту `COleDataSource` функцию, чтобы очистить объект данных.

```
void Empty();
```

### <a name="remarks"></a>Remarks

Форматы кэшированных и задержки рендеринга опорожняются, чтобы их можно было использовать повторно.

Для получения дополнительной информации, [см. ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium) в Windows SDK.

## <a name="coledatasourceflushclipboard"></a><a name="flushclipboard"></a>ColeDataИсточник::FlushClipboard

Renders данные, которые находится на Clipboard, а затем позволяет вставить данные из Clipboard после выключения приложения.

```
static void PASCAL FlushClipboard();
```

### <a name="remarks"></a>Remarks

Используйте [SetClipboard](#setclipboard) для передачи данных на Clipboard.

## <a name="coledatasourcegetclipboardowner"></a><a name="getclipboardowner"></a>ColeDataИсточник::GetClipboardВладелец

Определяет, изменялись ли данные на Clipboard с момента последнего вызова [SetClipboard,](#setclipboard) и если да, то идентифицирует текущего владельца.

```
static COleDataSource* PASCAL GetClipboardOwner();
```

### <a name="return-value"></a>Возвращаемое значение

Источник данных в настоящее время на Clipboard, или NULL, если нет ничего на Clipboard или если Clipboard не принадлежит вызывающей заявке.

## <a name="coledatasourceonrenderdata"></a><a name="onrenderdata"></a>ColeDataИсточник::OnRenderData

Вызывается рамкой для извлечения данных в указанном формате.

```
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Параметры

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) с указанием формата, в котором запрашивается информация.

*lpStgMedium*<br/>
Указывает на структуру [STGMEDIUM,](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) в которой данные должны быть возвращены.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Указанный формат — это `COleDataSource` тот, который ранее размещался в объекте с использованием функции члена [DelayRenderData](#delayrenderdata) или [DelayRenderFileData](#delayrenderfiledata) для задержки рендеринга. Реализация этой функции по умолчанию будет вызывать [OnRenderFileData](#onrenderfiledata) или [OnRenderGlobalData,](#onrenderglobaldata) если поставляемый носитель хранения является файлом или памятью, соответственно. Если ни один из этих форматов не поставляется, то реализация по умолчанию вернет 0 и ничего не сделает. Для получения дополнительной информации о задержке рендеринга, обрабатываемых MFC, см. [Data Objects and Data Sources: Manipulation](../../mfc/data-objects-and-data-sources-manipulation.md)

Если *lpgMedium*-> *запечатля* `STGMEDIUM` TYMED_NULL, то должно быть выделено и заполнено в том виде, в каком указано *lpFormatEtc->.* Если он не TYMED_NULL, `STGMEDIUM` то должен быть заполнен на месте с данными.

Это передовой overridable. Переопределить эту функцию для предоставления данных в запрашиваемом формате и среде. В зависимости от ваших данных, вы можете переопределить одну из других версий этой функции вместо этого. Если ваши данные малы и фиксированные по размеру, переопределить. `OnRenderGlobalData` Если данные находится в файле или имеют `OnRenderFileData`переменный размер, переопределить .

Для получения дополнительной информации см. структуры [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) и [FORMATETC,](/windows/win32/api/objidl/ns-objidl-formatetc) тип перечисления [TYMED](/windows/win32/api/objidl/ne-objidl-tymed) и [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) в SDK Windows.

## <a name="coledatasourceonrenderfiledata"></a><a name="onrenderfiledata"></a>ColeDataИсточник::OnrenderFileData

Вызывается фреймворцом для извлечения данных в указанном формате, когда указанный носитель хранения является файлом.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>Параметры

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) с указанием формата, в котором запрашивается информация.

*pFile*<br/>
Указывает на объект [CFile,](../../mfc/reference/cfile-class.md) в котором данные должны быть отрисованы.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Указанный формат предварительно размещен `COleDataSource` в объекте с использованием функции члена [DelayRenderData](#delayrenderdata) для задержки рендеринга. Реализация этой функции по умолчанию просто возвращает FALSE.

Это передовой overridable. Переопределить эту функцию для предоставления данных в запрашиваемом формате и среде. В зависимости от ваших данных, вы можете переопределить одну из других версий этой функции вместо этого. Если вы хотите обрабатывать несколько носителей, переопределить [OnRenderData](#onrenderdata). Если данные находится в файле или имеют `OnRenderFileData`переменный размер, переопределить . Для получения дополнительной информации о задержке рендеринга, обрабатываемых MFC, см. [Data Objects and Data Sources: Manipulation](../../mfc/data-objects-and-data-sources-manipulation.md)

Для получения дополнительной информации см. структуру [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) и [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) в SDK Windows.

## <a name="coledatasourceonrenderglobaldata"></a><a name="onrenderglobaldata"></a>ColeDataИсточник::OnrenderGlobalData

Вызывается фреймворцом для извлечения данных в указанном формате, когда указанная среда хранения является глобальной памятью.

```
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,
    HGLOBAL* phGlobal);
```

### <a name="parameters"></a>Параметры

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) с указанием формата, в котором запрашивается информация.

*phGlobal*<br/>
Указывает на ручку глобальной памяти, в которой данные должны быть возвращены. Если один из них еще не выделен, этот параметр может быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Указанный формат предварительно размещен `COleDataSource` в объекте с использованием функции члена [DelayRenderData](#delayrenderdata) для задержки рендеринга. Реализация этой функции по умолчанию просто возвращает FALSE.

Если *phGlobal* является NULL, то новый HGLOBAL должен быть выделен и возвращен в *phGlobal*. В противном случае HGLOBAL, указанный *phGlobal,* должен быть заполнен данными. Объем данных, размещенных в HGLOBAL, не должен превышать текущий размер блока памяти. Кроме того, блок не может быть перераспределен в больший размер.

Это передовой overridable. Переопределить эту функцию для предоставления данных в запрашиваемом формате и среде. В зависимости от ваших данных, вы можете переопределить одну из других версий этой функции вместо этого. Если вы хотите обрабатывать несколько носителей, переопределить [OnRenderData](#onrenderdata). Если данные находится в файле или имеют переменный размер, переопределить [OnRenderFileData.](#onrenderfiledata) Для получения дополнительной информации о задержке рендеринга, обрабатываемых MFC, см. [Data Objects and Data Sources: Manipulation](../../mfc/data-objects-and-data-sources-manipulation.md)

Для получения дополнительной информации см. структуру [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) и [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) в SDK Windows.

## <a name="coledatasourceonsetdata"></a><a name="onsetdata"></a>ColeDataИсточник::OnsetData

Вызывается фреймворцом для `COleDataSource` установки или замены данных в объекте в указанном формате.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>Параметры

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) с указанием формата, в котором заменяются данные.

*lpStgMedium*<br/>
Указывает на структуру [STGMEDIUM,](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) содержащую данные, которые заменят текущее содержимое `COleDataSource` объекта.

*bRelease*<br/>
Указывает, кто владеет носителем хранения после завершения вызова функции. Звонящий решает, кто несет ответственность за выделение ресурсов, выделенных от имени носителя. Вызывающий абонент делает это, установив *bRelease.* Если *bRelease* является ненулевым, источник данных берет на себя право собственности, освобождая среду, когда он закончил использовать его. Когда *bRelease* равен 0, абонент сохраняет право собственности, а источник данных может использовать среду хранения только на время вызова.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Источник данных не берет на себя ответственность за данные до тех пор, пока он не успешно получил их. То есть, он не `OnSetData` берет на себя ответственность, если возвращает 0. Если источник данных берет на себя право собственности, он освобождает среду хранения, позвонив в функцию [ReleaseStgMedium.](/windows/win32/api/ole2/nf-ole2-releasestgmedium)

Реализация по умолчанию не выполняет никаких действий. Переопределить эту функцию для замены данных в указанном формате. Это передовой overridable.

Для получения дополнительной информации см. структуры [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) и [FORMATETC,](/windows/win32/api/objidl/ns-objidl-formatetc) а также [функции ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium) и [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) в SDK Windows.

## <a name="coledatasourcesetclipboard"></a><a name="setclipboard"></a>ColeDataИсточник::SetClipboard

Помещает данные, `COleDataSource` содержащиеся в объекте, на clipboard после вызова одной из следующих функций: [CacheData,](#cachedata) [CacheGlobalData,](#cacheglobaldata) [DelayRenderData](#delayrenderdata)или [DelayRenderFile.](#delayrenderfiledata)

```
void SetClipboard();
```

## <a name="see-also"></a>См. также раздел

[MFC Образец HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDataObject](../../mfc/reference/coledataobject-class.md)
