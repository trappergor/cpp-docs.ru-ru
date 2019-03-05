---
title: Класс CPrintDialog
ms.date: 11/04/2016
f1_keywords:
- CPrintDialog
- AFXDLGS/CPrintDialog
- AFXDLGS/CPrintDialog::CPrintDialog
- AFXDLGS/CPrintDialog::CreatePrinterDC
- AFXDLGS/CPrintDialog::DoModal
- AFXDLGS/CPrintDialog::GetCopies
- AFXDLGS/CPrintDialog::GetDefaults
- AFXDLGS/CPrintDialog::GetDeviceName
- AFXDLGS/CPrintDialog::GetDevMode
- AFXDLGS/CPrintDialog::GetDriverName
- AFXDLGS/CPrintDialog::GetFromPage
- AFXDLGS/CPrintDialog::GetPortName
- AFXDLGS/CPrintDialog::GetPrinterDC
- AFXDLGS/CPrintDialog::GetToPage
- AFXDLGS/CPrintDialog::PrintAll
- AFXDLGS/CPrintDialog::PrintCollate
- AFXDLGS/CPrintDialog::PrintRange
- AFXDLGS/CPrintDialog::PrintSelection
- AFXDLGS/CPrintDialog::m_pd
helpviewer_keywords:
- CPrintDialog [MFC], CPrintDialog
- CPrintDialog [MFC], CreatePrinterDC
- CPrintDialog [MFC], DoModal
- CPrintDialog [MFC], GetCopies
- CPrintDialog [MFC], GetDefaults
- CPrintDialog [MFC], GetDeviceName
- CPrintDialog [MFC], GetDevMode
- CPrintDialog [MFC], GetDriverName
- CPrintDialog [MFC], GetFromPage
- CPrintDialog [MFC], GetPortName
- CPrintDialog [MFC], GetPrinterDC
- CPrintDialog [MFC], GetToPage
- CPrintDialog [MFC], PrintAll
- CPrintDialog [MFC], PrintCollate
- CPrintDialog [MFC], PrintRange
- CPrintDialog [MFC], PrintSelection
- CPrintDialog [MFC], m_pd
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
ms.openlocfilehash: b6fd633a39f7038be45a8776c9b4673138cc34b5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274951"
---
# <a name="cprintdialog-class"></a>Класс CPrintDialog

Инкапсулирует службы, предоставляемые стандартным диалоговым окном Windows для печати.

## <a name="syntax"></a>Синтаксис

```
class CPrintDialog : public CCommonDialog
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CPrintDialog::CPrintDialog](#cprintdialog)|Создает объект `CPrintDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|Создает контекст устройства принтера без отображения диалогового окна печати.|
|[CPrintDialog::DoModal](#domodal)|Отображает диалоговое окно и позволяет пользователю сделать выбор.|
|[CPrintDialog::GetCopies](#getcopies)|Извлекает число копий, в запросе.|
|[CPrintDialog::GetDefaults](#getdefaults)|Получает значения по умолчанию устройства не отображение диалогового окна.|
|[CPrintDialog::GetDeviceName](#getdevicename)|Получает имя текущего выбранного принтера.|
|[CPrintDialog::GetDevMode](#getdevmode)|Извлекает `DEVMODE` структуры.|
|[CPrintDialog::GetDriverName](#getdrivername)|Получает имя текущего выбранного драйвера.|
|[CPrintDialog::GetFromPage](#getfrompage)|Получает начальную страницу диапазона.|
|[CPrintDialog::GetPortName](#getportname)|Извлекает имя порта текущий выбранный принтер.|
|[CPrintDialog::GetPrinterDC](#getprinterdc)|Извлекает дескриптор контекст устройства принтера.|
|[CPrintDialog::GetToPage](#gettopage)|Получает страницу конца диапазона.|
|[CPrintDialog::PrintAll](#printall)|Определяет, необходимо ли печатать все страницы документа.|
|[CPrintDialog::PrintCollate](#printcollate)|Определяет копий запрашиваются ли разбор по копиям.|
|[CPrintDialog::PrintRange](#printrange)|Определяет, надо ли выводить только указанный диапазон страниц.|
|[CPrintDialog::PrintSelection](#printselection)|Определяет, надо ли выводить только выбранные элементы.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CPrintDialog::m_pd](#m_pd)|Структура, используемая для настройки `CPrintDialog` объекта.|

## <a name="remarks"></a>Примечания

Поля общего диалогового окна печати предоставляют простой способ реализовать диалоговые окна печати и параметры печати в соответствии со стандартами Windows.

> [!NOTE]
>  `CPrintDialogEx` Класс инкапсулирует службы, предоставляемые вкладкой свойств печати Windows. Дополнительные сведения см. в разделе [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) Обзор.

`CPrintDialog`в функции, заменяется, [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md), разработанный для обеспечения общее диалоговое окно для обоих параметров печати и параметры страницы.

Можно положиться на платформу, чтобы заниматься многими аспектами процесс печати для вашего приложения. В этом случае платформа автоматически отображает Windows общее диалоговое окно для печати. Можно также иметь дескриптор framework печати для вашего приложения, но переопределить общее диалоговое окно печати с помощью собственных диалоговое окно печати. Дополнительные сведения об использовании платформой для обработки задач печати см. в статье [печати](../../mfc/printing.md).

Если требуется, чтобы приложение для обработки печати без участия платформы, можно использовать `CPrintDialog` класса с помощью конструктора, предоставленного «как есть», также можно вывести собственный класс диалогового окна из `CPrintDialog` и создание конструктора в соответствии с потребностями. В любом случае этим диалоговым окнам будет работать как стандартные диалоговые окна MFC, поскольку они являются производными от класса `CCommonDialog`.

Чтобы использовать `CPrintDialog` следует сначала создать объект с помощью `CPrintDialog` конструктор. После создания диалоговом окне можно задать или изменить значения в [m_pd](#m_pd) структуры для инициализации значений элементов управления диалогового окна. `m_pd` Структуры имеет тип [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda). Дополнительные сведения об этой структуре см. в разделе Windows SDK.

Если вы не предоставляете дескрипторов в `m_pd` для `hDevMode` и `hDevNames` члены, не забудьте вызвать функцию Windows `GlobalFree` для этих маркеров, когда вы закончите с диалоговым окном. При использовании реализации платформы параметры печати, предоставляемые `CWinApp::OnFilePrintSetup`, у вас нет для освобождения этих маркеров. Поддерживаемые маркеры `CWinApp` и освобождаются в `CWinApp`в деструктор. Требуется только для освобождения этих маркеров, при использовании `CPrintDialog` автономный.

После инициализации элементов окна, вызовите `DoModal` функция-член отображается диалоговое окно и позволяет пользователю выбрать параметры печати. `DoModal` Возвращает, является ли пользователь выбрал кнопку ОК (IDOK) или Отмена (IDCANCEL).

Если `DoModal` возвращает IDOK, можно использовать один из `CPrintDialog`в функции-члены для получения сведений, введенное пользователем.

`CPrintDialog::GetDefaults` Функция-член эффективно для получения текущих значений по умолчанию принтер без отображения диалоговое окно. Эта функция-член не требует вмешательства пользователя.

Можно использовать Windows `CommDlgExtendedError` функция для определения, произошла ли ошибка во время инициализации диалогового окна и Дополнительные сведения об ошибке. Дополнительные сведения по этой функции см. в разделе Windows SDK.

`CPrintDialog` использует COMMDLG. DLL-файл, который поставляется с Windows 3.1 и более поздних версиях.

Чтобы настроить в диалоговом окне, являются производными от класса `CPrintDialog`, предоставляют шаблон настраиваемое диалоговое окно и добавить схему сообщений для обработки сообщений уведомлений из расширенных элементов управления. Любые необработанные сообщения должны быть переданы базовый класс. Настройка функция-обработчик не является обязательным.

Чтобы обработать это сообщение по-разному в зависимости от является ли диалоговое окно печати или параметры печати, необходимо унаследовать класс в каждом диалоговом окне. Необходимо также переопределить Windows `AttachOnSetup` функцию, которая управляет созданием нового диалогового окна при нажатии кнопки Параметры печати в диалоговом окне печати.

Дополнительные сведения об использовании `CPrintDialog`, см. в разделе [классы общих диалоговых окон](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

##  <a name="cprintdialog"></a>  CPrintDialog::CPrintDialog

Создает объект диалоговое окно печати Windows или параметры печати.

```
CPrintDialog(
    BOOL bPrintSetupOnly,
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*bPrintSetupOnly*<br/>
Указывает, отображается ли стандартным диалоговым окном печати Windows или диалоговое окно настройки печати. Значение этого параметра значение true, если стандартное диалоговое окно настройки печати Windows. Ему присвоено значение FALSE, чтобы отобразить диалоговое окно печати Windows. Если *bPrintSetupOnly* имеет значение FALSE, параметры печати, переключатель по-прежнему отображается в диалоговом окне печати.

*dwFlags*<br/>
Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна, объединенные с помощью битового оператора или. Например флаг PD_ALLPAGES задает диапазон печати по умолчанию для всех страниц документа. См. в разделе [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) структуры в пакете SDK для Windows, Дополнительные сведения о эти флаги.

*pParentWnd*<br/>
Указатель на окно родительский объект или владельца диалогового окна.

### <a name="remarks"></a>Примечания

Только эта функция-член создает объект. Используйте `DoModal` функция-член для отображения в диалоговом окне.

Обратите внимание, что при вызове конструктора с *bPrintSetupOnly* задано значение FALSE, флаг PD_RETURNDC используется автоматически. После вызова метода `DoModal`, `GetDefaults`, или `GetPrinterDC`, принтера будет возвращаться в `m_pd.hDC`. Этот контроллер домена должен быть освобожден до этого вызовом [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) вызывающим объектом `CPrintDialog`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]

##  <a name="createprinterdc"></a>  CPrintDialog::CreatePrinterDC

Создает контекст устройства принтера (DC) из [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) и [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) структуры.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор контекста принтера на только что созданный.

### <a name="remarks"></a>Примечания

Предполагается, что этот контроллер домена является текущего принтера контроллера домена, и любые другие ранее полученный принтера, контроллеры домена должны быть удалены пользователем. Эту функцию можно вызывать и использовать полученный контроллера домена, без когда-нибудь отображения диалогового окна печати.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]

##  <a name="domodal"></a>  CPrintDialog::DoModal

Отображает общее диалоговое окно печати окно Windows и позволяет пользователю выбрать различные параметры печати, таких как количество копий, диапазон страниц и ли должен быть по копиям.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

IDOK и IDCANCEL. Если возвращается IDCANCEL, вызовите Windows [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) функцию, чтобы определить, произошла ли ошибка.

IDOK и IDCANCEL являются константы, указывающие, является ли пользователь выбрал кнопку ОК или "Отмена".

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различные параметры диалогового окна печати путем определения участников `m_pd` структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.

После вызова метода `DoModal`, можно вызвать другой член функции, чтобы получить параметры или данные, введенные пользователем в диалоговом окне.

Обратите внимание, что при вызове конструктора с *bPrintSetupOnly* задано значение FALSE, флаг PD_RETURNDC используется автоматически. После вызова метода `DoModal`, `GetDefaults`, или `GetPrinterDC`, принтера будет возвращаться в `m_pd.hDC`. Этот контроллер домена должен быть освобожден до этого вызовом [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) вызывающим объектом `CPrintDialog`.

### <a name="example"></a>Пример

  См. в примере [CPrintDialog::CreatePrinterDC](#createprinterdc).

##  <a name="getcopies"></a>  CPrintDialog::GetCopies

Извлекает число копий, в запросе.

```
int GetCopies() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число копий, в запросе.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после вызова метода `DoModal` для получения количества сохраняемых копий запрошено.

### <a name="example"></a>Пример

  См. в примере [CPrintDialog::PrintCollate](#printcollate).

##  <a name="getdefaults"></a>  CPrintDialog::GetDefaults

Получает значения по умолчанию устройства принтера по умолчанию не отображение диалогового окна.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Полученные значения помещаются в `m_pd` структуры.

В некоторых случаях вызов этой функции будет вызывать [конструктор](#cprintdialog) для `CPrintDialog` с *bPrintSetupOnly* значение FALSE. В этих случаях принтера и `hDevNames` и `hDevMode` (двух дескрипторов находится в `m_pd` данные-член) выделяются автоматически.

Если конструктор для `CPrintDialog` был вызван с *bPrintSetupOnly* задано значение FALSE, эта функция не только возвращает `hDevNames` и `hDevMode` в `m_pd.hDevNames` и `m_pd.hDevMode`) вызывающему объекту, но также возвращает принтера в `m_pd.hDC`. Он отвечает за вызывающему объекту удалить принтер DC и вызывать Windows [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree) функция дескрипторах при завершении работы с `CPrintDialog` объекта.

### <a name="example"></a>Пример

Этот фрагмент кода получает контекст устройства принтера по умолчанию и сообщает пользователю разрешение принтера в точках на дюйм. (Этот атрибут возможности принтера часто называется точек на ДЮЙМ.)

[!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]

##  <a name="getdevicename"></a>  CPrintDialog::GetDeviceName

Получает имя текущего выбранного принтера.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя выбранного принтера.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после вызова метода [DoModal](#domodal) получить имя текущего выбранного принтера или после вызова метода [GetDefaults](#getdefaults) для получения текущих значений по умолчанию устройства принтера по умолчанию. Использование указателя на `CString` объект, возвращаемый `GetDeviceName` для параметра `lpszDeviceName` в вызове [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

### <a name="example"></a>Пример

Этот фрагмент кода показывает имя принтера по умолчанию для пользователя и порт, к которому он подключен, а также имя очереди печати принтера. Код может показывать окно сообщения об ошибке: «принтер по умолчанию включен HP LaserJet IIIP \\\server\share с помощью winspool.», например.

[!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]

##  <a name="getdevmode"></a>  CPrintDialog::GetDevMode

Извлекает `DEVMODE` структуры.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

[DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) структуру данных, которая содержит сведения об инициализации устройства и среду драйвер принтера. Чтобы разблокировать память, занимаемую эту структуру с Windows [GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock) функции, который описан в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) для получения сведений об устройстве печати.

### <a name="example"></a>Пример

  См. в примере [CPrintDialog::PrintCollate](#printcollate).

##  <a name="getdrivername"></a>  CPrintDialog::GetDriverName

Получает имя текущего выбранного драйвера.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` Указание имени драйвера, определенная системой.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) получить имя драйвер принтера, определенная системой. Использование указателя на `CString` объект, возвращаемый `GetDriverName` для параметра `lpszDriverName` в вызове [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

### <a name="example"></a>Пример

  См. в примере [CPrintDialog::GetDeviceName](#getdevicename).

##  <a name="getfrompage"></a>  CPrintDialog::GetFromPage

Получает начальную страницу диапазона.

```
int GetFromPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер домашней страницы в диапазоне страниц для печати.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после вызова метода `DoModal` для получения номер домашней страницы в диапазоне страниц для печати.

### <a name="example"></a>Пример

  См. в примере [CPrintDialog::m_pd](#m_pd).

##  <a name="getportname"></a>  CPrintDialog::GetPortName

Извлекает имя порта текущий выбранный принтер.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя порта текущий выбранный принтер.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) получить имя порта текущий выбранный принтер.

### <a name="example"></a>Пример

  См. в примере [CPrintDialog::GetDeviceName](#getdevicename).

##  <a name="getprinterdc"></a>  CPrintDialog::GetPrinterDC

Извлекает дескриптор контекст устройства принтера.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор контекста устройства принтера, если выполнение прошло успешно; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

Если *bPrintSetupOnly* параметр `CPrintDialog` конструктор был FALSE (указывает, что отображается диалоговое окно «Печать»), затем `GetPrinterDC` возвращает дескриптор контекста устройства принтера. Необходимо вызвать Windows [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) функции, чтобы удалить контекст устройства, когда вы закончите его использования.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]

##  <a name="gettopage"></a>  CPrintDialog::GetToPage

Получает страницу конца диапазона.

```
int GetToPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер конечной страницы в диапазоне страниц для печати.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после вызова метода `DoModal` для получения номер конечной страницы в диапазоне страниц для печати.

### <a name="example"></a>Пример

  См. в примере [CPrintDialog::m_pd](#m_pd).

##  <a name="m_pd"></a>  CPrintDialog::m_pd

Структура, члены которой хранения характеристики объекта диалогового окна.

```
PRINTDLG& m_pd;
```

### <a name="remarks"></a>Примечания

После построения `CPrintDialog` объекта, можно использовать `m_pd` для задания различных аспектов диалоговом окне перед вызовом [DoModal](#domodal) функция-член. Дополнительные сведения о `m_pd` структуры, см. в разделе [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) в пакете Windows SDK.

При изменении `m_pd` элемент данных напрямую, переопределяет любое поведение по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]

##  <a name="printall"></a>  CPrintDialog::PrintAll

Определяет, необходимо ли печатать все страницы документа.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если все страницы в документе для печати; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после вызова метода `DoModal` для определения необходимости печати всех страниц в документе.

### <a name="example"></a>Пример

  См. в примере [CPrintDialog::m_pd](#m_pd).

##  <a name="printcollate"></a>  CPrintDialog::PrintCollate

Определяет копий запрашиваются ли разбор по копиям.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь выбирает флажок collate в диалоговом окне; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после вызова метода `DoModal` для определения, следует ли принтер collate все печатные копии документа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]

##  <a name="printrange"></a>  CPrintDialog::PrintRange

Определяет, надо ли выводить только указанный диапазон страниц.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если только диапазон страниц в документе для печати; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после вызова метода `DoModal` чтобы определить, надо ли выводить только диапазон страниц в документе.

### <a name="example"></a>Пример

  См. в примере [CPrintDialog::m_pd](#m_pd).

##  <a name="printselection"></a>  CPrintDialog::PrintSelection

Определяет, надо ли выводить только выбранные элементы.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если только выбранные элементы для печати; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после вызова метода `DoModal` чтобы определить, надо ли выводить только выбранные элементы.

### <a name="example"></a>Пример

  См. в примере [CPrintDialog::m_pd](#m_pd).

## <a name="see-also"></a>См. также

[Пример MFC DIBLOOK](../../visual-cpp-samples.md)<br/>
[Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Структура CPrintInfo](../../mfc/reference/cprintinfo-structure.md)
