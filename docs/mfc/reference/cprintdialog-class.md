---
title: Класс Кпринтдиалог
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
ms.openlocfilehash: ab194b1c289f8347243b36354f4f314b7450a7aa
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916902"
---
# <a name="cprintdialog-class"></a>Класс Кпринтдиалог

Инкапсулирует службы, предоставляемые стандартным диалоговым окном Windows для печати.

## <a name="syntax"></a>Синтаксис

```
class CPrintDialog : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CPrintDialog::CPrintDialog](#cprintdialog)|Создает объект `CPrintDialog`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|Создает контекст печатающего устройства, не отображая диалоговое окно Печать.|
|[CPrintDialog::DoModal](#domodal)|Отображает диалоговое окно и позволяет пользователю сделать выбор.|
|[CPrintDialog::GetCopies](#getcopies)|Возвращает количество запрошенных копий.|
|[CPrintDialog::GetDefaults](#getdefaults)|Извлекает значения по умолчанию для устройств без отображения диалогового окна.|
|[CPrintDialog::GetDeviceName](#getdevicename)|Извлекает имя выбранного в данный момент принтера.|
|[CPrintDialog::GetDevMode](#getdevmode)|`DEVMODE` Извлекает структуру.|
|[CPrintDialog::GetDriverName](#getdrivername)|Извлекает имя выбранного в данный момент драйвера принтера.|
|[CPrintDialog::GetFromPage](#getfrompage)|Извлекает начальную страницу диапазона печати.|
|[CPrintDialog::GetPortName](#getportname)|Извлекает имя выбранного в данный момент порта принтера.|
|[CPrintDialog::GetPrinterDC](#getprinterdc)|Извлекает маркер контекста устройства принтера.|
|[CPrintDialog::GetToPage](#gettopage)|Извлекает конечную страницу диапазона печати.|
|[CPrintDialog::PrintAll](#printall)|Определяет, следует ли печатать все страницы документа.|
|[CPrintDialog::PrintCollate](#printcollate)|Определяет, запрашиваются ли копии по копиям.|
|[CPrintDialog::PrintRange](#printrange)|Определяет, следует ли печатать только указанный диапазон страниц.|
|[CPrintDialog::PrintSelection](#printselection)|Определяет, следует ли печатать только выбранные в данный момент элементы.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CPrintDialog::m_pd](#m_pd)|Структура, используемая для настройки `CPrintDialog` объекта.|

## <a name="remarks"></a>Примечания

Общие диалоговые окна печати предоставляют простой способ реализации диалоговых окон печати и печати в соответствии со стандартами Windows.

> [!NOTE]
>  `CPrintDialogEx` Класс инкапсулирует службы, предоставляемые страницей свойств печати Windows. Дополнительные сведения см. в обзоре [кпринтдиаложекс](../../mfc/reference/cprintdialogex-class.md) .

`CPrintDialog`заменяется функцией [кпажесетупдиалог](../../mfc/reference/cpagesetupdialog-class.md), которая предназначена для предоставления общего диалогового окна для настройки печати и настройки страницы.

Вы можете использовать платформу для обработки многих аспектов процесса печати приложения. В этом случае платформа автоматически отображает общее диалоговое окно Windows для печати. Кроме того, платформа может выполнять печать для приложения, но переопределять общее диалоговое окно печати с помощью собственного диалогового окна печати. Дополнительные сведения об использовании платформы для работы с задачами печати см. в статье [Печать](../../mfc/printing.md).

Если вы хотите, чтобы приложение обрабатывал печать без участия в платформе, можно использовать `CPrintDialog` класс "как есть" с предоставленным конструктором или создать собственный класс диалогового окна из `CPrintDialog` и написать конструктор в соответствии с вашими потребностями. В любом случае эти диалоговые окна будут вести себя так же, как стандартные диалоговые окна MFC, `CCommonDialog`поскольку они являются производными от класса.

Чтобы использовать `CPrintDialog` объект, сначала создайте объект `CPrintDialog` с помощью конструктора. После создания диалогового окна можно задать или изменить любые значения в структуре [m_pd](#m_pd) , чтобы инициализировать значения элементов управления диалогового окна. Структура `m_pd` имеет тип [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda). Дополнительные сведения об этой структуре см. в Windows SDK.

Если вы не `m_pd` предоставляете собственные дескрипторы `hDevMode` для членов и `hDevNames` , не забудьте вызвать функцию `GlobalFree` Windows для этих дескрипторов после завершения работы с диалоговым окном. При использовании реализации настройки печати платформы `CWinApp::OnFilePrintSetup`, предоставляемой, не нужно освобождать эти дескрипторы. Дескрипторы поддерживаются `CWinApp` и `CWinApp`освобождаются деструктором. Эти дескрипторы необходимо освобождать только при использовании `CPrintDialog` автономных.

После инициализации элементов управления диалогового окна вызовите `DoModal` функцию члена, чтобы открыть диалоговое окно и позволить пользователю выбрать параметры печати. `DoModal`Возвращает значение, указывающее, выбрал пользователь кнопку ОК (ИДОК) или Отмена (ИДКАНЦЕЛ).

Если `DoModal` функция возвращает идок, для получения входных `CPrintDialog`данных пользователем можно использовать одну из функций члена.

Функция `CPrintDialog::GetDefaults` -член полезна для получения текущих значений по умолчанию для принтера без отображения диалогового окна. Эта функция члена не требует вмешательства пользователя.

С помощью функции Windows `CommDlgExtendedError` можно определить, произошла ли ошибка во время инициализации диалогового окна, и получить дополнительные сведения об ошибке. Дополнительные сведения об этой функции см. в Windows SDK.

`CPrintDialog`полагается на КОММДЛГ. DLL-файл, поставляемый с Windows версии 3,1 и более поздних версий.

Чтобы настроить диалоговое окно, создайте производный класс от `CPrintDialog`, предоставьте пользовательский шаблон диалогового окна и добавьте карту сообщений для обработки сообщений уведомлений из расширенных элементов управления. Все необработанные сообщения должны передаваться в базовый класс. Настройка функции-обработчика не является обязательной.

Для обработки одного и того же сообщения по-разному в зависимости от того, является ли диалоговое окно печатью или настройкой печати, необходимо создать класс для каждого диалогового окна. Также необходимо переопределить функцию Windows `AttachOnSetup` , которая обрабатывает создание нового диалогового окна, когда в диалоговом окне Печать выбрана кнопка Настройка печати.

Дополнительные сведения об использовании `CPrintDialog`см. в разделе [Общие классы диалоговых окон](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[ккоммондиалог](../../mfc/reference/ccommondialog-class.md)

`CPrintDialog`

## <a name="requirements"></a>Требования

**Заголовок:** афксдлгс. h

##  <a name="cprintdialog"></a>  CPrintDialog::CPrintDialog

Создание объекта диалогового окна печати или настройки печати Windows.

```
CPrintDialog(
    BOOL bPrintSetupOnly,
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*бпринтсетупонли*<br/>
Указывает, отображается ли стандартное диалоговое окно печати Windows или диалоговое окно «Настройка печати». Задайте для этого параметра значение TRUE, чтобы отобразить стандартное диалоговое окно настройки печати Windows. Задайте для него значение FALSE, чтобы отобразить диалоговое окно Печать Windows. Если *бпринтсетупонли* имеет значение false, то в диалоговом окне Печать по-прежнему отображается кнопка Параметры печати.

*dwFlags*<br/>
Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна в сочетании с помощью побитового оператора или. Например, флаг PD_ALLPAGES устанавливает диапазон печати по умолчанию для всех страниц документа. Дополнительные сведения об этих флагах см. в описании структуры [принтдлг](/windows/desktop/api/commdlg/ns-commdlg-tagpda) в Windows SDK.

*ппарентвнд*<br/>
Указатель на родительский узел или окно-владелец диалогового окна.

### <a name="remarks"></a>Примечания

Эта функция члена конструирует только объект. Используйте функцию `DoModal` члена для вывода диалогового окна.

Обратите внимание, что при вызове конструктора с параметром *бпринтсетупонли* , для которого ЗАДАНО значение false, флаг PD_RETURNDC используется автоматически. После вызова `DoModal`, `GetDefaults`или `GetPrinterDC`контроллер домена будет возвращен в `m_pd.hDC`. Этот контроллер домена должен быть освобожден с помощью вызова [делетедк](/windows/desktop/api/wingdi/nf-wingdi-deletedc) вызывающим объектом `CPrintDialog`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]

##  <a name="createprinterdc"></a>  CPrintDialog::CreatePrinterDC

Создает контекст устройства принтера (DC) из структур [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) и [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) .

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Возвращаемое значение

Обработайте с созданным контекстом печатающего устройства.

### <a name="remarks"></a>Примечания

Предполагается, что контроллер домена является текущим контроллером домена, а все ранее полученные контроллеры домена должны быть удалены пользователем. Эта функция может быть вызвана, и полученный контроллер домена будет использоваться без отображения диалогового окна «Печать».

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]

##  <a name="domodal"></a>  CPrintDialog::DoModal

Отображает диалоговое окно обычный печать Windows, позволяющее пользователю выбирать различные параметры печати, такие как количество копий, диапазон страниц и необходимость сортировки копий.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

ИДОК или ИДКАНЦЕЛ. Если возвращается ИДКАНЦЕЛ, вызовите функцию Windows [коммдлжекстендедеррор](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) , чтобы определить, произошла ли ошибка.

ИДОК и ИДКАНЦЕЛ — это константы, которые указывают, выбрал ли пользователь кнопку ОК или Отмена.

### <a name="remarks"></a>Примечания

Если требуется инициализировать различные параметры диалогового окна печати путем установки элементов `m_pd` структуры, следует сделать это перед вызовом метода `DoModal`, но после создания объекта диалогового окна.

После вызова `DoModal`можно вызвать другие функции члена для получения параметров или данных, вводимых пользователем, в диалоговое окно.

Обратите внимание, что при вызове конструктора с параметром *бпринтсетупонли* , для которого ЗАДАНО значение false, флаг PD_RETURNDC используется автоматически. После вызова `DoModal`, `GetDefaults`или `GetPrinterDC`контроллер домена будет возвращен в `m_pd.hDC`. Этот контроллер домена должен быть освобожден с помощью вызова [делетедк](/windows/desktop/api/wingdi/nf-wingdi-deletedc) вызывающим объектом `CPrintDialog`.

### <a name="example"></a>Пример

  См. пример для [кпринтдиалог:: креатепринтердк](#createprinterdc).

##  <a name="getcopies"></a>  CPrintDialog::GetCopies

Возвращает количество запрошенных копий.

```
int GetCopies() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число запрошенных копий.

### <a name="remarks"></a>Примечания

Вызовите эту функцию после `DoModal` вызова, чтобы получить количество запрошенных копий.

### <a name="example"></a>Пример

  См. пример для [кпринтдиалог::P ринтколлате](#printcollate).

##  <a name="getdefaults"></a>  CPrintDialog::GetDefaults

Возвращает параметры по умолчанию для принтера по умолчанию без отображения диалогового окна.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Извлеченные значения помещаются в `m_pd` структуру.

В некоторых случаях вызов этой функции вызывает [конструктор](#cprintdialog) для `CPrintDialog` с параметром WITH *бпринтсетупонли* , имеющим значение false. В таких случаях контроллеры домена и `hDevNames` `hDevMode` ( `m_pd` два маркера, расположенных в члене данных) автоматически распределяются.

Если конструктор для `CPrintDialog` был вызван с параметром *бпринтсетупонли* , для которого задано значение false, эта `hDevNames` функция не будет `m_pd.hDevNames` возвращать вызывающему объекту и `hDevMode` находиться в `m_pd.hDevMode`нем, но также будет возвращать контроллер домена в `m_pd.hDC`. Ответственность за удаление контроллера домена принтера и вызов функции Windows [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree) для дескрипторов после завершения работы с `CPrintDialog` объектом.

### <a name="example"></a>Пример

Этот фрагмент кода получает контекст устройства принтера по умолчанию и сообщает пользователю разрешение принтера в точках на дюйм. (Этот атрибут возможностей принтера часто называется DPI.)

[!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]

##  <a name="getdevicename"></a>  CPrintDialog::GetDeviceName

Извлекает имя выбранного в данный момент принтера.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя выбранного в данный момент принтера.

### <a name="remarks"></a>Примечания

Вызовите эту функцию после вызова [DoModal](#domodal) , чтобы получить имя текущего выбранного принтера, или после вызова метода [Default](#getdefaults) , чтобы получить текущие значения по умолчанию для принтера по умолчанию. Используйте указатель на `CString` объект, `GetDeviceName` возвращаемый в качестве значения `lpszDeviceName` в вызове [CDC:: креатедк](../../mfc/reference/cdc-class.md#createdc).

### <a name="example"></a>Пример

Этот фрагмент кода показывает имя принтера пользователя по умолчанию и порт, к которому он подключен, а также имя диспетчера очереди печати. В коде может отображаться окно сообщения "ваш принтер по умолчанию — HP LaserJet ииип On \\\сервер\шаре using винспул.", например.

[!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]

##  <a name="getdevmode"></a>  CPrintDialog::GetDevMode

`DEVMODE` Извлекает структуру.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Структура данных [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) , которая содержит сведения об инициализации устройства и среде драйвера печати. Необходимо разблокировать память, занятую этой структурой, с помощью функции Windows [глобалунлокк](/windows/desktop/api/winbase/nf-winbase-globalunlock) , которая описана в Windows SDK.

### <a name="remarks"></a>Примечания

Вызовите эту функцию после вызова [DoModal](#domodal) или [по умолчанию](#getdefaults) , чтобы получить сведения о печатающем устройстве.

### <a name="example"></a>Пример

  См. пример для [кпринтдиалог::P ринтколлате](#printcollate).

##  <a name="getdrivername"></a>  CPrintDialog::GetDriverName

Извлекает имя выбранного в данный момент драйвера принтера.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение `CString` типа, указывающее имя драйвера, определяемое системой.

### <a name="remarks"></a>Примечания

Вызовите эту функцию после вызова [DoModal](#domodal) или [по умолчанию](#getdefaults) , чтобы получить имя драйвера принтера, определенного системой. Используйте указатель на `CString` объект, `GetDriverName` возвращаемый в качестве значения `lpszDriverName` в вызове [CDC:: креатедк](../../mfc/reference/cdc-class.md#createdc).

### <a name="example"></a>Пример

  См. пример для [кпринтдиалог:: жетдевиценаме](#getdevicename).

##  <a name="getfrompage"></a>  CPrintDialog::GetFromPage

Извлекает начальную страницу диапазона печати.

```
int GetFromPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер начальной страницы в диапазоне печатаемых страниц.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после `DoModal` вызова, чтобы получить номер начальной страницы в диапазоне печатаемых страниц.

### <a name="example"></a>Пример

  См. пример для [кпринтдиалог:: m_pd](#m_pd).

##  <a name="getportname"></a>  CPrintDialog::GetPortName

Извлекает имя выбранного в данный момент порта принтера.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя выбранного в данный момент порта принтера.

### <a name="remarks"></a>Примечания

Вызовите эту функцию после вызова [DoModal](#domodal) или [по умолчанию](#getdefaults) , чтобы получить имя выбранного в данный момент порта принтера.

### <a name="example"></a>Пример

  См. пример для [кпринтдиалог:: жетдевиценаме](#getdevicename).

##  <a name="getprinterdc"></a>  CPrintDialog::GetPrinterDC

Извлекает маркер контекста устройства принтера.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Возвращаемое значение

Маркер контекста устройства принтера в случае успешного выполнения; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Если `CPrintDialog` параметр *бпринтсетупонли* конструктора имеет значение false (что означает, что отображается диалоговое окно Печать), то `GetPrinterDC` возвращает маркер контекста устройства принтера. Чтобы удалить контекст устройства после завершения его использования, необходимо вызвать функцию Windows [делетедк](/windows/desktop/api/wingdi/nf-wingdi-deletedc) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]

##  <a name="gettopage"></a>  CPrintDialog::GetToPage

Извлекает конечную страницу диапазона печати.

```
int GetToPage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Номер конечной страницы в диапазоне печатаемых страниц.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после `DoModal` вызова метода, чтобы получить номер конечной страницы в диапазоне печатаемых страниц.

### <a name="example"></a>Пример

  См. пример для [кпринтдиалог:: m_pd](#m_pd).

##  <a name="m_pd"></a>  CPrintDialog::m_pd

Структура, члены которой хранят характеристики объекта диалогового окна.

```
PRINTDLG& m_pd;
```

### <a name="remarks"></a>Примечания

После создания `CPrintDialog` объекта можно использовать `m_pd` для установки различных аспектов диалогового окна перед вызовом функции-члена [DoModal](#domodal) . Дополнительные сведения `m_pd` о структуре см. в разделе [принтдлг](/windows/desktop/api/commdlg/ns-commdlg-tagpda) в Windows SDK.

При непосредственном изменении `m_pd` элемента данных будет переопределено поведение по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]

##  <a name="printall"></a>  CPrintDialog::PrintAll

Определяет, следует ли печатать все страницы документа.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если все страницы документа должны печататься; в противном случае — 0.

### <a name="remarks"></a>Примечания

Вызовите эту функцию после `DoModal` вызова, чтобы определить, следует ли печатать все страницы в документе.

### <a name="example"></a>Пример

  См. пример для [кпринтдиалог:: m_pd](#m_pd).

##  <a name="printcollate"></a>  CPrintDialog::PrintCollate

Определяет, запрашиваются ли копии по копиям.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь нажимает флажок COLLATE в диалоговом окне; в противном случае — 0.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после `DoModal` вызова, чтобы определить, должен ли принтер выполнять сортировку всех печатных копий документа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]

##  <a name="printrange"></a>  CPrintDialog::PrintRange

Определяет, следует ли печатать только указанный диапазон страниц.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если требуется напечатать только диапазон страниц документа. в противном случае — 0.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после `DoModal` вызова, чтобы определить, следует ли печатать в документе только диапазон страниц.

### <a name="example"></a>Пример

  См. пример для [кпринтдиалог:: m_pd](#m_pd).

##  <a name="printselection"></a>Кпринтдиалог::P Ринтселектион

Определяет, следует ли печатать только выбранные в данный момент элементы.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если будут распечатаны только выбранные элементы; в противном случае — 0.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию после `DoModal` вызова, чтобы определить, следует ли печатать только выбранные в данный момент элементы.

### <a name="example"></a>Пример

  См. пример для [кпринтдиалог:: m_pd](#m_pd).

## <a name="see-also"></a>См. также

[Пример DIBLOOK в MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Структура CPrintInfo](../../mfc/reference/cprintinfo-structure.md)
