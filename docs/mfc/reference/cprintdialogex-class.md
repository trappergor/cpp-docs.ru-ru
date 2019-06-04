---
title: Класс CPrintDialogEx
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
ms.openlocfilehash: 3959eb01e5c0a36410129925e7c3f53898e99196
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504803"
---
# <a name="cprintdialogex-class"></a>Класс CPrintDialogEx

Инкапсулирует службы, предоставляемые вкладкой свойств печати Windows.

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
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|Создает контекст устройства принтера без отображения диалогового окна печати.|
|[CPrintDialogEx::DoModal](#domodal)|Отображает диалоговое окно и пользователь может выбирать.|
|[CPrintDialogEx::GetCopies](#getcopies)|Извлекает число копий, в запросе.|
|[CPrintDialogEx::GetDefaults](#getdefaults)|Получает значения по умолчанию устройства не отображение диалогового окна.|
|[CPrintDialogEx::GetDeviceName](#getdevicename)|Получает имя текущего выбранного принтера.|
|[CPrintDialogEx::GetDevMode](#getdevmode)|Извлекает `DEVMODE` структуры.|
|[CPrintDialogEx::GetDriverName](#getdrivername)|Извлекает имя драйвер принтера, определенная системой.|
|[CPrintDialogEx::GetPortName](#getportname)|Извлекает имя порта текущий выбранный принтер.|
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Извлекает дескриптор контекст устройства принтера.|
|[CPrintDialogEx::PrintAll](#printall)|Определяет, необходимо ли печатать все страницы документа.|
|[CPrintDialogEx::PrintCollate](#printcollate)|Определяет копий запрашиваются ли разбор по копиям.|
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|Определяет, следует ли печать текущей страницы документа.|
|[CPrintDialogEx::PrintRange](#printrange)|Определяет, надо ли выводить только указанный диапазон страниц.|
|[CPrintDialogEx::PrintSelection](#printselection)|Определяет, надо ли выводить только выбранные элементы.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CPrintDialogEx::m_pdex](#m_pdex)|Структура, используемая для настройки `CPrintDialogEx` объекта.|

## <a name="remarks"></a>Примечания

Можно положиться на платформу, чтобы заниматься многими аспектами процесс печати для вашего приложения. Дополнительные сведения об использовании платформой для обработки задач печати см. в статье [печати](../../mfc/printing.md).

Если требуется, чтобы приложение для обработки печати без участия платформы, можно использовать `CPrintDialogEx` класса с помощью конструктора, предоставленного «как есть», также можно вывести собственный класс диалогового окна из `CPrintDialogEx` и создание конструктора в соответствии с потребностями. В любом случае этим диалоговым окнам будет работать как стандартные диалоговые окна MFC, поскольку они являются производными от класса `CCommonDialog`.

Чтобы использовать `CPrintDialogEx` следует сначала создать объект с помощью `CPrintDialogEx` конструктор. После создания диалоговом окне можно задать или изменить значения в [m_pdex](#m_pdex) структуры для инициализации значений элементов управления диалогового окна. `m_pdex` Структуры имеет тип [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa). Дополнительные сведения об этой структуре см. в разделе Windows SDK.

Если вы не предоставляете дескрипторов в `m_pdex` для `hDevMode` и `hDevNames` члены, не забудьте вызвать функцию Windows `GlobalFree` для этих маркеров, когда вы закончите с диалоговым окном.

После инициализации элементов окна, вызовите `DoModal` функция-член отображается диалоговое окно и позволяет пользователю выбрать параметры печати. Когда `DoModal` возвращает, можно определить, является ли пользователь выбрал кнопку ОК "," Применить "или" Отмена.

Если пользователь нажал OK, вы можете использовать `CPrintDialogEx`в функции-члены для получения сведений, введенное пользователем.

`CPrintDialogEx::GetDefaults` Функция-член эффективно для получения текущих значений по умолчанию принтер без отображения диалоговое окно. Этот метод не требует вмешательства пользователя.

Можно использовать Windows `CommDlgExtendedError` функция для определения, произошла ли ошибка во время инициализации диалогового окна и Дополнительные сведения об ошибке. Дополнительные сведения по этой функции см. в разделе Windows SDK.

Дополнительные сведения об использовании `CPrintDialogEx`, см. в разделе [классы общих диалоговых окон](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`IObjectWithSite`

`IPrintDialogCallback`

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialogEx`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

##  <a name="cprintdialogex"></a>  CPrintDialogEx::CPrintDialogEx

Создает таблицу свойств печати Windows.

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна, объединенные с помощью битового оператора или. Например флаг PD_ALLPAGES задает диапазон печати по умолчанию для всех страниц документа. См. в разделе [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) структуры в пакете SDK для Windows, Дополнительные сведения о эти флаги.

*pParentWnd*<br/>
Указатель на окно родительский объект или владельца диалогового окна.

### <a name="remarks"></a>Примечания

Только эта функция-член создает объект. Используйте `DoModal` функция-член для отображения в диалоговом окне.

##  <a name="createprinterdc"></a>  CPrintDialogEx::CreatePrinterDC

Создает контекст устройства принтера (DC) из [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) и [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) структуры.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор контекста принтера на только что созданный.

### <a name="remarks"></a>Примечания

Возвращенный контроллер домена также хранятся в `hDC` членом [m_pdex](#m_pdex).

Предполагается, что этот контроллер домена является текущего принтера контроллера домена, и любые другие ранее полученный принтера, контроллеры домена должны быть удалены. Эту функцию можно вызывать и использовать полученный контроллера домена, без когда-нибудь отображения диалогового окна печати.

##  <a name="domodal"></a>  CPrintDialogEx::DoModal

Вызывайте эту функцию для отображения страницы свойств печати Windows и разрешить пользователю выбирать различные параметры печати, таких как количество копий, диапазон страниц и ли должен быть по копиям.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

INT_PTR возвращаемое значение — фактически значение HRESULT. См. в разделе возвращают значения в [PrintDlgEx](/previous-versions/windows/desktop/legacy/ms646942\(v=vs.85\)) в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различные параметры диалогового окна печати путем определения участников `m_pdex` структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.

После вызова метода `DoModal`, можно вызвать другой член функции, чтобы получить параметры или данные, введенные пользователем в диалоговом окне.

Если флаг PD_RETURNDC используется при вызове `DoModal`, принтера будет возвращаться в `hDC` членом [m_pdex](#m_pdex). Этот контроллер домена должен быть освобожден до этого вызовом [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) вызывающим объектом `CPrintDialogEx`.

##  <a name="getcopies"></a>  CPrintDialogEx::GetCopies

Вызывайте эту функцию после вызова метода `DoModal` для получения количества сохраняемых копий запрошено.

```
int GetCopies() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число копий, в запросе.

##  <a name="getdefaults"></a>  CPrintDialogEx::GetDefaults

Вызывайте эту функцию для получения значения по умолчанию устройства принтера по умолчанию без отображения диалоговое окно.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно, в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Создает контекст устройства принтера (DC) из [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) и [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) структуры.

`GetDefaults` не отображать окно свойств печати. Вместо этого он задает `hDevNames` и `hDevMode` членами [m_pdex](#m_pdex) для дескрипторов к [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) и [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) структур, которые были инициализированы для принтер по умолчанию системы. Оба `hDevNames` и `hDevMode` должен иметь значение NULL, или `GetDefaults` завершается ошибкой.

Если флаг PD_RETURNDC установлен, эта функция не только возвращает `hDevNames` и `hDevMode` (расположенный в `m_pdex.hDevNames` и `m_pdex.hDevMode`) вызывающей стороне, но также возвратит принтера в `m_pdex.hDC`. Он отвечает за вызывающему объекту удалить принтер DC и вызывать Windows [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree) функция дескрипторах при завершении работы с `CPrintDialogEx` объекта.

##  <a name="getdevicename"></a>  CPrintDialogEx::GetDeviceName

Вызывайте эту функцию после вызова метода [DoModal](#domodal) получить имя текущего выбранного принтера или после вызова метода [GetDefaults](#getdefaults) для извлечения имени принтера по умолчанию.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя выбранного принтера.

### <a name="remarks"></a>Примечания

Использование указателя на `CString` объект, возвращаемый `GetDeviceName` для параметра `lpszDeviceName` в вызове [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getdevmode"></a>  CPrintDialogEx::GetDevMode

Вызывайте эту функцию после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) для получения сведений об устройстве печати.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

[DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) структуру данных, которая содержит сведения об инициализации устройства и среду драйвер принтера. Чтобы разблокировать память, занимаемую эту структуру с Windows [GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock) функции, который описан в пакете Windows SDK.

##  <a name="getdrivername"></a>  CPrintDialogEx::GetDriverName

Вызывайте эту функцию после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) получить имя драйвер принтера, определенная системой.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` Указание имени драйвера, определенная системой.

### <a name="remarks"></a>Примечания

Использование указателя на `CString` объект, возвращаемый `GetDriverName` для параметра *lpszDriverName* в вызове [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getportname"></a>  CPrintDialogEx::GetPortName

Вызывайте эту функцию после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) получить имя порта текущий выбранный принтер.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя порта текущий выбранный принтер.

##  <a name="getprinterdc"></a>  CPrintDialogEx::GetPrinterDC

Возвращает дескриптор контекста устройства принтера.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор контекста принтера.

### <a name="remarks"></a>Примечания

Необходимо вызвать Windows [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) функции, чтобы удалить контекст устройства, когда вы закончите его использования.

##  <a name="m_pdex"></a>  CPrintDialogEx::m_pdex

Структура PRINTDLGEX, члены которой хранения характеристики объекта диалогового окна.

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>Примечания

После построения `CPrintDialogEx` объекта, можно использовать `m_pdex` для задания различных аспектов диалоговом окне перед вызовом [DoModal](#domodal) функция-член. Дополнительные сведения о `m_pdex` структуры, см. в разделе [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) в пакете Windows SDK.

При изменении `m_pdex` элемент данных напрямую, переопределяет любое поведение по умолчанию.

##  <a name="printall"></a>  CPrintDialogEx::PrintAll

Вызывайте эту функцию после вызова метода `DoModal` для определения необходимости печати всех страниц в документе.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если все страницы документа на печать; в противном случае — значение FALSE.

##  <a name="printcollate"></a>  CPrintDialogEx::PrintCollate

Вызывайте эту функцию после вызова метода `DoModal` для определения, следует ли принтер collate все печатные копии документа.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если пользователь выбирает флажок collate в диалоговом окне; в противном случае — значение FALSE.

##  <a name="printcurrentpage"></a>  CPrintDialogEx::PrintCurrentPage

Вызывайте эту функцию после вызова метода `DoModal` для определения необходимости напечатать текущую страницу в документе.

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если **печати текущей страницы** находится выбрана в диалоговом окне печати; в противном случае — значение FALSE.

##  <a name="printrange"></a>  CPrintDialogEx::PrintRange

Вызывайте эту функцию после вызова метода `DoModal` чтобы определить, надо ли выводить только диапазон страниц в документе.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если только диапазон страниц в документе для печати; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Можно определить диапазоны указанную страницу из [m_pdex](#m_pdex) (см. в разделе `nPageRanges`, `nMaxPageRanges`, и `lpPageRanges` в [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) структуры в пакете SDK для Windows).

##  <a name="printselection"></a>  CPrintDialogEx::PrintSelection

Вызывайте эту функцию после вызова метода `DoModal` чтобы определить, надо ли выводить только выбранные элементы.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если только выбранные элементы для печати; в противном случае — значение FALSE.

## <a name="see-also"></a>См. также

[Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Структура CPrintInfo](../../mfc/reference/cprintinfo-structure.md)
