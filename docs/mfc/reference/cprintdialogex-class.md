---
title: Класс Кпринтдиаложекс
ms.date: 11/04/2016
f1_keywords:
- CPrintDialogEx
- AFXDLGS/CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CreatePrinterDC
- AFXDLGS/CPrintDialogEx::DoModal
- AFXDLGS/CPrintDialogEx::GetCopies
- AFXDLGS/CPrintDialogEx::GetDefaults
- AFXDLGS/CPrintDialogEx::GetDeviceName
- AFXDLGS/CPrintDialogEx::GetDevMode
- AFXDLGS/CPrintDialogEx::GetDriverName
- AFXDLGS/CPrintDialogEx::GetPortName
- AFXDLGS/CPrintDialogEx::GetPrinterDC
- AFXDLGS/CPrintDialogEx::PrintAll
- AFXDLGS/CPrintDialogEx::PrintCollate
- AFXDLGS/CPrintDialogEx::PrintCurrentPage
- AFXDLGS/CPrintDialogEx::PrintRange
- AFXDLGS/CPrintDialogEx::PrintSelection
- AFXDLGS/CPrintDialogEx::m_pdex
helpviewer_keywords:
- CPrintDialogEx [MFC], CPrintDialogEx
- CPrintDialogEx [MFC], CreatePrinterDC
- CPrintDialogEx [MFC], DoModal
- CPrintDialogEx [MFC], GetCopies
- CPrintDialogEx [MFC], GetDefaults
- CPrintDialogEx [MFC], GetDeviceName
- CPrintDialogEx [MFC], GetDevMode
- CPrintDialogEx [MFC], GetDriverName
- CPrintDialogEx [MFC], GetPortName
- CPrintDialogEx [MFC], GetPrinterDC
- CPrintDialogEx [MFC], PrintAll
- CPrintDialogEx [MFC], PrintCollate
- CPrintDialogEx [MFC], PrintCurrentPage
- CPrintDialogEx [MFC], PrintRange
- CPrintDialogEx [MFC], PrintSelection
- CPrintDialogEx [MFC], m_pdex
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
ms.openlocfilehash: 76c3968b20a66e9653fd769339e23ede2a756bbd
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741332"
---
# <a name="cprintdialogex-class"></a>Класс Кпринтдиаложекс

Инкапсулирует службы, предоставляемые страницей свойств печати Windows.

## <a name="syntax"></a>Синтаксис

```
class CPrintDialogEx : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|Создает объект `CPrintDialogEx`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|Создает контекст печатающего устройства, не отображая диалоговое окно Печать.|
|[CPrintDialogEx::DoModal](#domodal)|Отображает диалоговое окно и позволяет пользователю выбрать нужные элементы.|
|[CPrintDialogEx::GetCopies](#getcopies)|Возвращает количество запрошенных копий.|
|[CPrintDialogEx::GetDefaults](#getdefaults)|Извлекает значения по умолчанию для устройств без отображения диалогового окна.|
|[CPrintDialogEx::GetDeviceName](#getdevicename)|Извлекает имя выбранного в данный момент принтера.|
|[CPrintDialogEx::GetDevMode](#getdevmode)|`DEVMODE` Извлекает структуру.|
|[CPrintDialogEx::GetDriverName](#getdrivername)|Возвращает имя драйвера устройства печати, определенного системой.|
|[CPrintDialogEx::GetPortName](#getportname)|Извлекает имя выбранного в данный момент порта принтера.|
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Извлекает маркер контекста устройства принтера.|
|[CPrintDialogEx::PrintAll](#printall)|Определяет, следует ли печатать все страницы документа.|
|[CPrintDialogEx::PrintCollate](#printcollate)|Определяет, запрашиваются ли копии по копиям.|
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|Определяет, следует ли печатать текущую страницу документа.|
|[CPrintDialogEx::PrintRange](#printrange)|Определяет, следует ли печатать только указанный диапазон страниц.|
|[CPrintDialogEx::PrintSelection](#printselection)|Определяет, следует ли печатать только выбранные в данный момент элементы.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CPrintDialogEx::m_pdex](#m_pdex)|Структура, используемая для настройки `CPrintDialogEx` объекта.|

## <a name="remarks"></a>Примечания

Вы можете использовать платформу для обработки многих аспектов процесса печати приложения. Дополнительные сведения об использовании платформы для работы с задачами печати см. в статье [Печать](../../mfc/printing.md).

Если вы хотите, чтобы приложение обрабатывал печать без участия в платформе, можно использовать `CPrintDialogEx` класс "как есть" с предоставленным конструктором или создать собственный класс диалогового окна из `CPrintDialogEx` и написать конструктор в соответствии с вашими потребностями. В любом случае эти диалоговые окна будут вести себя так же, как стандартные диалоговые окна MFC, `CCommonDialog`поскольку они являются производными от класса.

Чтобы использовать `CPrintDialogEx` объект, сначала создайте объект `CPrintDialogEx` с помощью конструктора. После создания диалогового окна можно задать или изменить любые значения в структуре [m_pdex](#m_pdex) , чтобы инициализировать значения элементов управления диалогового окна. Структура `m_pdex` имеет тип [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw). Дополнительные сведения об этой структуре см. в Windows SDK.

Если вы не `m_pdex` предоставляете собственные дескрипторы `hDevMode` для членов и `hDevNames` , не забудьте вызвать функцию `GlobalFree` Windows для этих дескрипторов после завершения работы с диалоговым окном.

После инициализации элементов управления диалогового окна вызовите `DoModal` функцию члена, чтобы открыть диалоговое окно и позволить пользователю выбрать параметры печати. При `DoModal` возврате можно определить, выбрал ли пользователь кнопку ОК, применить или Отмена.

Если пользователь нажал кнопку ОК, можно использовать `CPrintDialogEx`функции члена, чтобы получить данные, введенные пользователем.

Функция `CPrintDialogEx::GetDefaults` -член полезна для получения текущих значений по умолчанию для принтера без отображения диалогового окна. Этот метод не требует вмешательства пользователя.

С помощью функции Windows `CommDlgExtendedError` можно определить, произошла ли ошибка во время инициализации диалогового окна, и получить дополнительные сведения об ошибке. Дополнительные сведения об этой функции см. в Windows SDK.

Дополнительные сведения об использовании `CPrintDialogEx`см. в разделе [Общие классы диалоговых окон](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`IObjectWithSite`

`IPrintDialogCallback`

[ккоммондиалог](../../mfc/reference/ccommondialog-class.md)

`CPrintDialogEx`

## <a name="requirements"></a>Требования

**Заголовок:** афксдлгс. h

##  <a name="cprintdialogex"></a>  CPrintDialogEx::CPrintDialogEx

Создание страницы свойств печати Windows.

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна в сочетании с помощью побитового оператора или. Например, флаг PD_ALLPAGES устанавливает диапазон печати по умолчанию для всех страниц документа. Дополнительные сведения об этих флагах см. в описании структуры [принтдлжекс](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) в Windows SDK.

*ппарентвнд*<br/>
Указатель на родительский узел или окно-владелец диалогового окна.

### <a name="remarks"></a>Примечания

Эта функция члена конструирует только объект. Используйте функцию `DoModal` члена для вывода диалогового окна.

##  <a name="createprinterdc"></a>  CPrintDialogEx::CreatePrinterDC

Создает контекст устройства принтера (DC) из структур [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) и [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) .

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Возвращаемое значение

Обработайте с созданным контекстом печатающего устройства.

### <a name="remarks"></a>Примечания

Возвращенный контроллер домена также хранится в `hDC` члене [m_pdex](#m_pdex).

Предполагается, что контроллер домена является текущим контроллером домена, и все остальные ранее полученные контроллеры домена должны быть удалены. Эта функция может быть вызвана, и полученный контроллер домена будет использоваться без отображения диалогового окна «Печать».

##  <a name="domodal"></a>  CPrintDialogEx::DoModal

Эта функция вызывается для отображения страницы свойств печати Windows и позволяет пользователю выбирать различные параметры печати, такие как количество копий, диапазон страниц, а также следует ли выполнять сортировку по копиям.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение INT_PTR на самом деле является HRESULT. См. раздел возвращаемые значения в [принтдлжекс](/previous-versions/windows/desktop/legacy/ms646942\(v=vs.85\)) в Windows SDK.

### <a name="remarks"></a>Примечания

Если требуется инициализировать различные параметры диалогового окна печати путем установки элементов `m_pdex` структуры, следует сделать это перед вызовом метода `DoModal`, но после создания объекта диалогового окна.

После вызова `DoModal`можно вызвать другие функции члена для получения параметров или данных, вводимых пользователем, в диалоговое окно.

Если при вызове `DoModal`используется флаг PD_RETURNDC, то `hDC` в члене [m_pdex](#m_pdex)будет возвращен контроллер домена. Этот контроллер домена должен быть освобожден с помощью вызова [делетедк](/windows/win32/api/wingdi/nf-wingdi-deletedc) вызывающим объектом `CPrintDialogEx`.

##  <a name="getcopies"></a>  CPrintDialogEx::GetCopies

Вызовите эту функцию после `DoModal` вызова, чтобы получить количество запрошенных копий.

```
int GetCopies() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число запрошенных копий.

##  <a name="getdefaults"></a>  CPrintDialogEx::GetDefaults

Вызывайте эту функцию для получения значений по умолчанию для принтера по умолчанию без отображения диалогового окна.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если выполнено успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Создает контекст устройства принтера (DC) из структур [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) и [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) .

`GetDefaults`не отображает страницу свойств печать. Вместо этого он `hDevNames` задает члены и `hDevMode` [m_pdex](#m_pdex) для обработки структур [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) и [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) , инициализированных для принтера системы по умолчанию. Оба `hDevNames` значения `hDevMode` и должны иметь значение NULL `GetDefaults` или выдавать ошибку.

Если установлен флаг PD_RETURNDC, эта `hDevNames` функция не будет возвращать вызывающему объекту и `hDevMode` (находится `m_pdex.hDevNames` в `m_pdex.hDevMode`и), но также будет возвращать контроллер домена в `m_pdex.hDC`. Ответственность за удаление контроллера домена принтера и вызов функции Windows [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree) для дескрипторов после завершения работы с `CPrintDialogEx` объектом.

##  <a name="getdevicename"></a>  CPrintDialogEx::GetDeviceName

Вызовите эту функцию после вызова [DoModal](#domodal) , чтобы получить имя текущего выбранного принтера, или после вызова метода [Default](#getdefaults) , чтобы получить имя принтера по умолчанию.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя выбранного в данный момент принтера.

### <a name="remarks"></a>Примечания

Используйте указатель на `CString` объект, `GetDeviceName` возвращаемый в качестве значения `lpszDeviceName` в вызове [CDC:: креатедк](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getdevmode"></a>  CPrintDialogEx::GetDevMode

Вызовите эту функцию после вызова [DoModal](#domodal) или [по умолчанию](#getdefaults) , чтобы получить сведения о печатающем устройстве.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Структура данных [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) , которая содержит сведения об инициализации устройства и среде драйвера печати. Необходимо разблокировать память, занятую этой структурой, с помощью функции Windows [глобалунлокк](/windows/win32/api/winbase/nf-winbase-globalunlock) , которая описана в Windows SDK.

##  <a name="getdrivername"></a>  CPrintDialogEx::GetDriverName

Вызовите эту функцию после вызова [DoModal](#domodal) или [по умолчанию](#getdefaults) , чтобы получить имя драйвера принтера, определенного системой.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение `CString` типа, указывающее имя драйвера, определяемое системой.

### <a name="remarks"></a>Примечания

`CString` Используйте указатель на объект `GetDriverName` , возвращаемый в качестве значения *лпсздривернаме* в вызове [CDC:: креатедк](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getportname"></a>  CPrintDialogEx::GetPortName

Вызовите эту функцию после вызова [DoModal](#domodal) или [по умолчанию](#getdefaults) , чтобы получить имя выбранного в данный момент порта принтера.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя выбранного в данный момент порта принтера.

##  <a name="getprinterdc"></a>  CPrintDialogEx::GetPrinterDC

Возвращает маркер контекста устройства принтера.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Возвращаемое значение

Маркер контекста устройства принтера.

### <a name="remarks"></a>Примечания

Чтобы удалить контекст устройства после завершения его использования, необходимо вызвать функцию Windows [делетедк](/windows/win32/api/wingdi/nf-wingdi-deletedc) .

##  <a name="m_pdex"></a>  CPrintDialogEx::m_pdex

Структура ПРИНТДЛЖЕКС, члены которой хранят характеристики объекта диалогового окна.

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>Примечания

После создания `CPrintDialogEx` объекта можно использовать `m_pdex` для установки различных аспектов диалогового окна перед вызовом функции-члена [DoModal](#domodal) . Дополнительные сведения `m_pdex` о структуре см. в разделе [принтдлжекс](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) в Windows SDK.

При непосредственном изменении `m_pdex` элемента данных будет переопределено поведение по умолчанию.

##  <a name="printall"></a>  CPrintDialogEx::PrintAll

Вызовите эту функцию после `DoModal` вызова, чтобы определить, следует ли печатать все страницы в документе.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если все страницы документа должны быть распечатаны; в противном случае — FALSE.

##  <a name="printcollate"></a>  CPrintDialogEx::PrintCollate

Вызывайте эту функцию после `DoModal` вызова, чтобы определить, должен ли принтер выполнять сортировку всех печатных копий документа.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если пользователь устанавливает флажок COLLATE в диалоговом окне; в противном случае — FALSE.

##  <a name="printcurrentpage"></a>  CPrintDialogEx::PrintCurrentPage

Вызовите эту функцию после `DoModal` вызова, чтобы определить, следует ли печатать текущую страницу в документе.

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если в диалоговом окне печати выбран параметр **Печать текущей страницы** ; в противном случае — FALSE.

##  <a name="printrange"></a>  CPrintDialogEx::PrintRange

Вызывайте эту функцию после `DoModal` вызова, чтобы определить, следует ли печатать в документе только диапазон страниц.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если требуется напечатать только диапазон страниц документа. в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Указанные диапазоны страниц можно определить из [m_pdex](#m_pdex) ( `nPageRanges`см., `nMaxPageRanges`и `lpPageRanges` в структуре [принтдлжекс](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) в Windows SDK).

##  <a name="printselection"></a>Кпринтдиаложекс::P Ринтселектион

Вызывайте эту функцию после `DoModal` вызова, чтобы определить, следует ли печатать только выбранные в данный момент элементы.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если должны быть распечатаны только выбранные элементы; в противном случае — FALSE.

## <a name="see-also"></a>См. также

[Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Структура CPrintInfo](../../mfc/reference/cprintinfo-structure.md)
