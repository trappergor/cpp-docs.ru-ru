---
title: "Класс CPrintDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7834351533cac7f518f5ce5f5558a6be2da34be
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="cprintdialog-class"></a>Класс CPrintDialog
Инкапсулирует службы, предоставляемые стандартным диалоговым окном Windows для печати.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPrintDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPrintDialog::CPrintDialog](#cprintdialog)|Создает объект `CPrintDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|Создает контекст устройства принтера без отображения диалогового окна печати.|  
|[CPrintDialog::DoModal](#domodal)|Отображает диалоговое окно и пользователь может сделать выбор.|  
|[CPrintDialog::GetCopies](#getcopies)|Возвращает число копий запрошено.|  
|[CPrintDialog::GetDefaults](#getdefaults)|Получает значения по умолчанию устройства не отображение диалогового окна.|  
|[CPrintDialog::GetDeviceName](#getdevicename)|Извлекает имя выбранного принтера.|  
|[CPrintDialog::GetDevMode](#getdevmode)|Извлекает `DEVMODE` структуры.|  
|[CPrintDialog::GetDriverName](#getdrivername)|Извлекает имя выбранного драйвера.|  
|[CPrintDialog::GetFromPage](#getfrompage)|Получает начальную страницу диапазон печати.|  
|[CPrintDialog::GetPortName](#getportname)|Извлекает имя выбранного порта.|  
|[CPrintDialog::GetPrinterDC](#getprinterdc)|Получает дескриптор контекста устройства принтера.|  
|[CPrintDialog::GetToPage](#gettopage)|Получает конечную страницу диапазон печати.|  
|[CPrintDialog::PrintAll](#printall)|Определяет, следует ли печати всех страниц документа.|  
|[CPrintDialog::PrintCollate](#printcollate)|Определяет ли сопоставить запрашиваются копий.|  
|[CPrintDialog::PrintRange](#printrange)|Определяет, следует ли печать указанного диапазона страниц.|  
|[CPrintDialog::PrintSelection](#printselection)|Определяет, следует ли печати только выбранные элементы.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPrintDialog::m_pd](#m_pd)|Структура, используемая для настройки `CPrintDialog` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Общие печати диалоговые окна предоставляют простой способ реализации диалоговыми окнами печати и параметры печати в соответствии со стандартами Windows.  
  
> [!NOTE]
>  `CPrintDialogEx` Класс инкапсулирует службы, предоставляемые вкладкой свойств печати Windows. Дополнительные сведения см. [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) Обзор.  
  
 `CPrintDialog`его функциональность является замененные по [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md), разработанный для предоставления часто используемое диалоговое окно для обоих параметров печати и параметры страницы.  
  
 Можно положиться на платформе, чтобы обрабатывать различные аспекты процесс печати для вашего приложения. В этом случае платформа автоматически отображает стандартным диалоговым окном Windows для печати. Могут также иметь дескриптор framework печати для вашего приложения, но переопределить стандартным диалоговым окном печати с собственного диалогового окна печати. Дополнительные сведения об использовании платформы для обработки заданий печати см. в статье [печати](../../mfc/printing.md).  
  
 Если требуется приложению обрабатывать печать без участия платформы, можно использовать `CPrintDialog` класса «как есть» с помощью конструктора, предоставленного или наследовании классов диалоговых окон из `CPrintDialog` и создание конструктора в соответствии с потребностями. В любом случае эти диалоговые будет работать как стандартные диалоговые окна MFC, так как они являются производными от класса `CCommonDialog`.  
  
 Для использования `CPrintDialog` объекта, сначала создайте объект с помощью `CPrintDialog` конструктор. После создания диалоговом окне можно задать или изменить значения в [m_pd](#m_pd) структуры для инициализации значений элементов управления в диалоговое окно «». `m_pd` Структуры имеет тип [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843). Дополнительные сведения о структуре см. в Windows SDK.  
  
 Если не указать дескрипторов в `m_pd` для **hDevMode** и **hDevNames** членов, нужно убедиться, что вызов функции Windows **GlobalFree** для этих маркеров Когда вы закончите с диалоговым окном. При использовании реализации framework Настройка печати, предоставляемые `CWinApp::OnFilePrintSetup`, нет необходимости освободить эти маркеры. Дескрипторы обслуживаются `CWinApp` и освобождаются в `CWinApp`деструктор. Необходим только для освобождения эти дескрипторы, при использовании `CPrintDialog` автономный.  
  
 После инициализации элементы управления диалоговых окон, вызовите метод `DoModal` функции-члена для отображения диалогового окна и разрешить пользователю выбирать параметры печати. `DoModal`Возвращает, является ли пользователь выбрал ОК ( **IDOK**) или "Отмена" ( **IDCANCEL**) кнопки.  
  
 Если `DoModal` возвращает **IDOK**, можно использовать один из `CPrintDialog`в функции-члены для извлечения информации, введенное пользователем.  
  
 `CPrintDialog::GetDefaults` Функция-член эффективно для получения текущего значения по умолчанию принтер без отображения диалоговое окно. Эта функция-член не требует вмешательства пользователя.  
  
 Можно использовать окна **CommDlgExtendedError** функции, чтобы определить, произошла ли ошибка во время инициализации диалогового окна и Дополнительные сведения об ошибке. Дополнительные сведения о данной функции см. в Windows SDK.  
  
 `CPrintDialog`использует COMMDLG. Файл DLL, который поставляется вместе с Windows версии 3.1 и более поздней версии.  
  
 Чтобы настроить диалоговое окно, создайте класс, производный от `CPrintDialog`, укажите шаблон настраиваемое диалоговое окно и добавить схему сообщений для обработки сообщений уведомлений из расширенных элементов управления. Любой необработанных сообщений должны быть переданы базовом классе. Функция-ловушка Настройка не требуется.  
  
 Чтобы обработать это сообщение по-разному в зависимости от того диалоговое окно печати или параметры печати, необходимо унаследовать класс для каждого диалогового окна. Необходимо также переопределить Windows **AttachOnSetup** функции, которая управляет созданием нового диалогового окна, при выборе кнопки Параметры печати в диалоговом окне печати.  
  
 Дополнительные сведения об использовании `CPrintDialog`, в разделе [классы общих диалоговых окон](../../mfc/common-dialog-classes.md).  
  
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
 Создает объект диалогового окна Параметры печати или печати Windows.  
  
```  
CPrintDialog(
    BOOL bPrintSetupOnly,  
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `bPrintSetupOnly`  
 Указывает, отображается ли стандартного диалогового окна печати Windows или параметры печати. Присвойте этому параметру значение **TRUE** для отображения стандартное диалоговое окно печати установки Windows. Задайте для него значение **FALSE** для отображения диалогового окна печати Windows. Если `bPrintSetupOnly` — **FALSE**, переключатель параметры печати по-прежнему отображается в окне «Печать».  
  
 `dwFlags`  
 Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна, объединенные с помощью оператора побитового или Например **PD_ALLPAGES** флаг задает диапазон печати по умолчанию для всех страниц документа. В разделе [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) структуры в Windows SDK, Дополнительные сведения об этих флагов.  
  
 `pParentWnd`  
 Указатель на диалоговое окно родительского или владельца.  
  
### <a name="remarks"></a>Примечания  
 Только эта функция-член создает объект. Используйте `DoModal` функции-члена для отображения диалогового окна.  
  
 Обратите внимание, что при вызове конструктора с `bPrintSetupOnly` значение **FALSE**, **PD_RETURNDC** флаг используется автоматически. После вызова метода `DoModal`, `GetDefaults`, или `GetPrinterDC`, будут возвращены принтера `m_pd.hDC`. Этот контроллер домена необходимо освободить с помощью вызова [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) вызывающим объектом `CPrintDialog`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>  CPrintDialog::CreatePrinterDC  
 Создает контекст устройства принтера (DC) из [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) и [DEVNAMES](../../mfc/reference/devnames-structure.md) структуры.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор контекста устройства только что созданный принтера.  
  
### <a name="remarks"></a>Примечания  
 Предполагается, что этот контроллер домена является текущей принтера и любые другие ранее получены принтер, контроллеры домена должны быть удалены пользователем. Эту функцию можно вызывать и использовать полученный контроллера домена без когда-либо отображения диалогового окна печати.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]  
  
##  <a name="domodal"></a>  CPrintDialog::DoModal  
 Отображает диалоговое окно Windows общих печати и позволяет пользователю выбирать различные параметры печати, например число копий, диапазон страниц и ли должно быть по копиям.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **IDOK** или **IDCANCEL**. Если **IDCANCEL** будет возвращен, вызовите Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) функцию, чтобы определить, произошла ли ошибка.  
  
 **IDOK** и **IDCANCEL** — константы, которые указывают, является ли пользователь выбрал кнопку OK или "Отмена".  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные параметры диалогового окна печати, задав члены `m_pd` структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 После вызова метода `DoModal`, можно вызывать другой член функции для получения параметров или данные, введенные пользователем в диалоговом окне.  
  
 Обратите внимание, что при вызове конструктора с `bPrintSetupOnly` значение **FALSE**, **PD_RETURNDC** флаг используется автоматически. После вызова метода `DoModal`, `GetDefaults`, или `GetPrinterDC`, будут возвращены принтера `m_pd.hDC`. Этот контроллер домена необходимо освободить с помощью вызова [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) вызывающим объектом `CPrintDialog`.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPrintDialog::CreatePrinterDC](#createprinterdc).  
  
##  <a name="getcopies"></a>  CPrintDialog::GetCopies  
 Возвращает число копий запрошено.  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число копий, в запросе.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` для получения количества сохраняемых копий запрошено.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPrintDialog::PrintCollate](#printcollate).  
  
##  <a name="getdefaults"></a>  CPrintDialog::GetDefaults  
 Получает значения по умолчанию устройства принтера по умолчанию не отображает диалоговое окно.  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Полученные значения помещаются в `m_pd` структуры.  
  
 В некоторых случаях вызов этой функции будет вызывать [конструктор](#cprintdialog) для `CPrintDialog` с `bPrintSetupOnly` значение **FALSE**. В этих случаях принтера и **hDevNames** и **hDevMode** (два маркера находится в `m_pd` элемент данных) выделяются автоматически.  
  
 Если конструктор `CPrintDialog` был вызван с `bPrintSetupOnly` значение **FALSE**, эта функция не вернет только **hDevNames** и **hDevMode** (в папке **m_pd.hDevNames** и **m_pd.hDevMode**) вызывающему объекту, но также возвращает принтера в **m_pd.hDC**. Отвечает вызывающего объекта, чтобы удалить принтер контроллера домена, а вызовите Windows [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) функция дескрипторах при завершении работы с `CPrintDialog` объекта.  
  
### <a name="example"></a>Пример  
 Этот фрагмент кода получает контекст устройства принтера по умолчанию и сообщает пользователю разрешение принтера в точках на дюйм. (Этот атрибут возможности принтера часто называют DPI.)  
  
 [!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]  
  
##  <a name="getdevicename"></a>  CPrintDialog::GetDeviceName  
 Извлекает имя выбранного принтера.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя выбранного принтера.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода [DoModal](#domodal) для извлечения имени выбранного принтера или после вызова метода [GetDefaults](#getdefaults) для извлечения текущих параметров устройства принтера по умолчанию. Используйте указатель `CString` объект, возвращаемый `GetDeviceName` в качестве значения `lpszDeviceName` при обращении к [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
### <a name="example"></a>Пример  
 Этот фрагмент кода показывает имя принтера по умолчанию для пользователя и порт, к которому он подключен, вместе с именем очереди печати принтера. Код может показывать окно сообщения об ошибке, «принтер по умолчанию включен HP LaserJet IIIP \\\server\share с помощью winspool.», например.  
  
 [!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]  
  
##  <a name="getdevmode"></a>  CPrintDialog::GetDevMode  
 Извлекает `DEVMODE` структуры.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) структуру данных, которая содержит сведения об инициализации устройства и среду драйвер принтера. Необходимо разблокировать память, занимаемую эту структуру с Windows [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) функции, которая описана в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) для получения сведений об устройстве печати.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPrintDialog::PrintCollate](#printcollate).  
  
##  <a name="getdrivername"></a>  CPrintDialog::GetDriverName  
 Извлекает имя выбранного драйвера.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` Указание имени драйвера, определенная системой.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) получить имя драйвер принтера, определенная системой. Используйте указатель `CString` объект, возвращаемый `GetDriverName` в качестве значения `lpszDriverName` при обращении к [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPrintDialog::GetDeviceName](#getdevicename).  
  
##  <a name="getfrompage"></a>  CPrintDialog::GetFromPage  
 Получает начальную страницу диапазон печати.  
  
```  
int GetFromPage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Начальный номер страницы диапазона страниц для печати.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` для извлечения начальный номер страницы в диапазоне печатаемых страниц.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="getportname"></a>  CPrintDialog::GetPortName  
 Извлекает имя выбранного порта.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя порта выбранного принтера.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) для извлечения имени выбранного порта.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPrintDialog::GetDeviceName](#getdevicename).  
  
##  <a name="getprinterdc"></a>  CPrintDialog::GetPrinterDC  
 Получает дескриптор контекста устройства принтера.  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор контекста устройства принтера в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если `bPrintSetupOnly` параметр `CPrintDialog` конструктор был **FALSE** (это означает, что отображается диалоговое окно «Печать»), затем `GetPrinterDC` возвращает дескриптор контекста устройства принтера. Необходимо вызвать Windows [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) , позволяющей удалить контекст устройства после завершения его использования.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]  
  
##  <a name="gettopage"></a>  CPrintDialog::GetToPage  
 Получает конечную страницу диапазон печати.  
  
```  
int GetToPage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Конечный номер страницы диапазона страниц для печати.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` для извлечения конечного номера страницы в диапазоне печатаемых страниц.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="m_pd"></a>  CPrintDialog::m_pd  
 Структуры, члены которого хранения характеристики объекта диалогового окна.  
  
```  
PRINTDLG& m_pd;  
```  
  
### <a name="remarks"></a>Примечания  
 После построения `CPrintDialog` объекта, можно использовать `m_pd` для задания различных аспектов диалоговым окном перед вызовом [DoModal](#domodal) функции-члена. Дополнительные сведения о `m_pd` структуры см. в разделе [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) в Windows SDK.  
  
 При изменении `m_pd` член данных напрямую, будут переопределяться любой по умолчанию.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]  
  
##  <a name="printall"></a>  CPrintDialog::PrintAll  
 Определяет, следует ли печати всех страниц документа.  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если все страницы в документе для печати; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` для определения необходимости печать всех страниц в документе.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="printcollate"></a>  CPrintDialog::PrintCollate  
 Определяет ли сопоставить запрашиваются копий.  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь выбирает флажок collate в диалоговом окне. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` для определения, следует ли принтер collate все печатные копии документа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]  
  
##  <a name="printrange"></a>  CPrintDialog::PrintRange  
 Определяет, следует ли печать указанного диапазона страниц.  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если только диапазон страниц в документе для печати; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` для определения необходимости напечатать диапазон страниц в документе.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="printselection"></a>  CPrintDialog::PrintSelection  
 Определяет, следует ли печати только выбранные элементы.  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если только выбранные элементы для печати; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` для определения необходимости печать только выбранных элементов.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPrintDialog::m_pd](#m_pd).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC DIBLOOK](../../visual-cpp-samples.md)   
 [Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Структура CPrintInfo](../../mfc/reference/cprintinfo-structure.md)
