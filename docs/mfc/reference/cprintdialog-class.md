---
title: "Класс CPrintDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- Print Setup dialog box
- Print dialog box
- CPrintDialog class
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: fe8b5a899169bf9dfd463278100384fde900a6a0
ms.lasthandoff: 02/24/2017

---
# <a name="cprintdialog-class"></a>Класс CPrintDialog
Инкапсулирует службы, предоставляемые стандартным диалоговым окном Windows для печати.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPrintDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPrintDialog::CPrintDialog](#cprintdialog)|Создает объект `CPrintDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|Создает контекст устройства принтера без отображения диалогового окна печати.|  
|[CPrintDialog::DoModal](#domodal)|Отображает диалоговое окно и позволяет пользователю сделать выбор.|  
|[CPrintDialog::GetCopies](#getcopies)|Получает количество запрошенных копий.|  
|[CPrintDialog::GetDefaults](#getdefaults)|Возвращает параметры устройства без Отображение диалогового окна.|  
|[CPrintDialog::GetDeviceName](#getdevicename)|Получает имя текущего выбранного принтера.|  
|[CPrintDialog::GetDevMode](#getdevmode)|Извлекает `DEVMODE` структуры.|  
|[CPrintDialog::GetDriverName](#getdrivername)|Получает имя текущего выбранного драйвера.|  
|[CPrintDialog::GetFromPage](#getfrompage)|Получает начальную страницу диапазон печати.|  
|[CPrintDialog::GetPortName](#getportname)|Получает имя текущего выбранного порта.|  
|[CPrintDialog::GetPrinterDC](#getprinterdc)|Возвращает дескриптор контекста устройства принтера.|  
|[CPrintDialog::GetToPage](#gettopage)|Получает конечную страницу диапазон печати.|  
|[CPrintDialog::PrintAll](#printall)|Определяет, следует ли печатать все страницы документа.|  
|[CPrintDialog::PrintCollate](#printcollate)|Определяет ли упорядоченную запросу копии.|  
|[CPrintDialog::PrintRange](#printrange)|Определяет, следует ли печать указанного диапазона страниц.|  
|[CPrintDialog::PrintSelection](#printselection)|Определяет, следует ли печатать только выбранные элементы.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPrintDialog::m_pd](#m_pd)|Структура, используемая для настройки `CPrintDialog` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Общие печати диалоговые окна предоставляют легкий способ применения диалоговые окна печати и параметры печати в соответствии со стандартами Windows.  
  
> [!NOTE]
>  `CPrintDialogEx` Класс инкапсулирует службы, предоставляемые вкладкой свойств печати Windows 2000. Дополнительные сведения см. [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) Обзор.  
  
 `CPrintDialog`в функции будет заменен по [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md), разработанный для обеспечения общее диалоговое окно для обоих параметров печати и параметры страницы.  
  
 Можно положиться на платформе заниматься многими аспектами процесса печати для вашего приложения. В этом случае платформа автоматически отображает стандартным диалоговым окном Windows для печати. Также можно иметь дескриптор framework печати для вашего приложения, но переопределить стандартным диалоговым окном печати собственного диалогового окна печати. Дополнительные сведения об использовании платформы для обработки заданий печати см. в статье [печати](../../mfc/printing.md).  
  
 Если требуется, чтобы приложение для обработки печати без участия framework, можно использовать `CPrintDialog` класса «как есть» с помощью конструктора, предоставленного или наследовании классов диалоговых окон с `CPrintDialog` и создание конструктора в соответствии с потребностями. В любом случае эти диалоговые будет работать как стандартные диалоговые окна MFC, поскольку они являются производными от класса `CCommonDialog`.  
  
 Для использования `CPrintDialog` объекта, сначала создайте объект с помощью `CPrintDialog` конструктор. После конструирования диалоговом окне можно задать или изменить какое-либо значение [m_pd](#m_pd) структуры для инициализации значений элементов управления диалогового окна. `m_pd` Структуры имеет тип [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843). Дополнительные сведения о структуре см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Если не указать дескрипторов в `m_pd` для **hDevMode** и **hDevNames** членов, необходимо вызвать функцию Windows **GlobalFree** для этих маркеров, после завершения работы с диалоговым окном. При использовании framework Настройка печати реализации `CWinApp::OnFilePrintSetup`, нет необходимости освободить эти маркеры. Маркеры поддерживаются `CWinApp` и освободить в `CWinApp`деструктор. Необходим только для освобождения этих маркеров, при использовании `CPrintDialog` автономный.  
  
 После инициализации диалоговыми окнами, вызовите `DoModal` функции-члена для отображения диалогового окна и разрешить пользователю выбирать параметры печати. `DoModal`Возвращает, выбрал ли пользователь ОК ( **IDOK**) или Отмена ( **IDCANCEL**) кнопки.  
  
 Если `DoModal` возвращает **IDOK**, можно использовать один из `CPrintDialog`функции-члены для извлечения информации, введенное пользователем.  
  
 `CPrintDialog::GetDefaults` Для получения текущего значения по умолчанию принтер без отображения диалогового полезна функция-член. Эта функция-член не требует вмешательства пользователя.  
  
 Можно использовать окна **CommDlgExtendedError** функции, чтобы определить, произошла ли ошибка во время инициализации диалогового окна и для получения дополнительных сведений об ошибке. Дополнительные сведения об этой функции см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `CPrintDialog`зависит от COMMDLG. DLL-файл, поставляемый с Windows версии 3.1 и более поздней версии.  
  
 Чтобы настроить диалоговое окно, создайте класс, производный от `CPrintDialog`, предоставить шаблон пользовательское диалоговое окно и добавить схемы сообщений для обработки сообщений уведомления из расширенных элементов управления. Все необработанные сообщения должны быть переданы базовом классе. Настройка функцию-обработчик не является обязательным.  
  
 Для обработки одного сообщения по-разному в зависимости от диалоговое окно печати или параметры печати, необходимо создать класс для каждого диалогового окна. Необходимо также переопределить Windows **AttachOnSetup** функции, которая управляет созданием нового диалогового окна, при выборе кнопки Параметры печати в диалоговом окне печати.  
  
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
  
##  <a name="cprintdialog"></a>CPrintDialog::CPrintDialog  
 Создает объект диалогового окна Настройка печати или печати Windows.  
  
```  
CPrintDialog(
    BOOL bPrintSetupOnly,  
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `bPrintSetupOnly`  
 Указывает, отображается ли стандартного диалогового окна печати Windows или диалоговое окно настройки печати. Присвойте этому параметру значение **TRUE** для отображения стандартное диалоговое окно Настройка печати Windows. Задайте для него значение **FALSE** для отображения диалогового окна печати Windows. Если `bPrintSetupOnly` — **FALSE**, переключатель Настройка печати по-прежнему отображается в диалоговом окне «Печать».  
  
 `dwFlags`  
 Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна, объединенные с помощью побитового оператора OR. Например **PD_ALLPAGES** флаг задает диапазон печати по умолчанию для всех страниц документа. В разделе [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения об этих флагов.  
  
 `pParentWnd`  
 Указатель на окне родительский или владельца диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член только создает объект. Используйте `DoModal` функции-члена для отображения диалогового окна.  
  
 Обратите внимание, что при вызове конструктора с `bPrintSetupOnly` значение **FALSE**, **PD_RETURNDC** автоматически используется флаг. После вызова метода `DoModal`, `GetDefaults`, или `GetPrinterDC`, принтер контроллера домена будут возвращены в `m_pd.hDC`. Этот контроллер домена должен быть освобожден с помощью вызова [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) вызывающим объектом `CPrintDialog`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#174;](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>CPrintDialog::CreatePrinterDC  
 Создает контекст устройства принтера (DC) из [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) и [DEVNAMES](../../mfc/reference/devnames-structure.md) структуры.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор контекста устройства, созданный принтера.  
  
### <a name="remarks"></a>Примечания  
 Предполагается, что этот контроллер домена является текущий принтер контроллера домена, и любые другие ранее полученные принтер, контроллеры доменов должны быть удалены пользователем. Эту функцию можно вызывать и использовать полученный контроллера домена без постоянно отображать диалоговое окно печати.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#106;](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]  
  
##  <a name="domodal"></a>CPrintDialog::DoModal  
 Отображает окно Общие диалогового окна печати Windows и позволяет пользователю выбирать различные параметры печати, такие как число копий, диапазон страниц и ли должно быть по копиям.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **IDOK** или **IDCANCEL**. Если **IDCANCEL** будет возвращен, вызовите Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) функцию, чтобы определить, произошла ли ошибка.  
  
 **IDOK** и **IDCANCEL** константы, которые указывают, выбрал ли пользователь кнопку OK или "Отмена".  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать параметры диалогового окна печати, задав члены `m_pd` структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 После вызова метода `DoModal`, можно вызвать другой член функции для получения параметров или данные, введенные пользователем в диалоговом окне.  
  
 Обратите внимание, что при вызове конструктора с `bPrintSetupOnly` значение **FALSE**, **PD_RETURNDC** автоматически используется флаг. После вызова метода `DoModal`, `GetDefaults`, или `GetPrinterDC`, принтер контроллера домена будут возвращены в `m_pd.hDC`. Этот контроллер домена должен быть освобожден с помощью вызова [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) вызывающим объектом `CPrintDialog`.  
  
### <a name="example"></a>Пример  
  В примере показано [CPrintDialog::CreatePrinterDC](#createprinterdc).  
  
##  <a name="getcopies"></a>CPrintDialog::GetCopies  
 Получает количество запрошенных копий.  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число копий, в запросе.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` для получения количества копий запрошено.  
  
### <a name="example"></a>Пример  
  В примере показано [CPrintDialog::PrintCollate](#printcollate).  
  
##  <a name="getdefaults"></a>CPrintDialog::GetDefaults  
 Получает значения по умолчанию устройства принтера по умолчанию не отображение диалогового окна.  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Полученные значения помещаются в `m_pd` структуру.  
  
 В некоторых случаях вызов этой функции будет вызывать [конструктор](#cprintdialog) для `CPrintDialog` с `bPrintSetupOnly` значение **FALSE**. В таких случаях принтер DC и **hDevNames** и **hDevMode** (два маркера находится в `m_pd` элемент данных) автоматически выделяются.  
  
 Если конструктор для `CPrintDialog` был вызван с `bPrintSetupOnly` значение **FALSE**, эта функция не возвращает только **hDevNames** и **hDevMode** (находится в **m_pd.hDevNames** и **m_pd.hDevMode**) вызывающему объекту, но возвратит принтера контроллера домена в **m_pd.hDC**. Отвечает вызывающего объекта, чтобы удалить принтер DC и вызвать Windows [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) функция дескрипторах при завершении работы с `CPrintDialog` объекта.  
  
### <a name="example"></a>Пример  
 Этот фрагмент кода получает контекст устройства принтер по умолчанию и сообщает пользователю разрешение принтера в точках на дюйм. (Этот атрибут возможностей принтера часто называют точек на ДЮЙМ.)  
  
 [!code-cpp[NVC_MFCDocView&#107;](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]  
  
##  <a name="getdevicename"></a>CPrintDialog::GetDeviceName  
 Получает имя текущего выбранного принтера.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя выбранного принтера.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода [DoModal](#domodal) для извлечения имени выбранного принтера или после вызова метода [GetDefaults](#getdefaults) для извлечения текущих параметров устройства принтера по умолчанию. Использование указателя для `CString` объект, возвращаемый `GetDeviceName` в качестве значения `lpszDeviceName` в вызове [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
### <a name="example"></a>Пример  
 Этот фрагмент кода показывает имя принтера по умолчанию для пользователя и порт, к которому он подключен, вместе с именем очереди печати принтера. Код может показывать окно сообщения с сообщением «принтер по умолчанию включен HP LaserJet IIIP \\\server\share с помощью winspool.», например.  
  
 [!code-cpp[NVC_MFCDocView&#108;](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]  
  
##  <a name="getdevmode"></a>CPrintDialog::GetDevMode  
 Извлекает `DEVMODE` структуры.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) структуру данных, которая содержит сведения об инициализации устройства и среде драйвер принтера. Необходимо разблокировать память, занимаемую структурой с Windows [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) функции, который описан в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) для получения сведений об устройстве печати.  
  
### <a name="example"></a>Пример  
  В примере показано [CPrintDialog::PrintCollate](#printcollate).  
  
##  <a name="getdrivername"></a>CPrintDialog::GetDriverName  
 Получает имя текущего выбранного драйвера.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `CString` Указание имени драйвера, определяемые системой.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) получить имя драйвера принтера, определяемые системой. Использование указателя для `CString` объект, возвращаемый `GetDriverName` в качестве значения `lpszDriverName` в вызове [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
### <a name="example"></a>Пример  
  В примере показано [CPrintDialog::GetDeviceName](#getdevicename).  
  
##  <a name="getfrompage"></a>CPrintDialog::GetFromPage  
 Получает начальную страницу диапазон печати.  
  
```  
int GetFromPage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Начальный номер страницы в диапазоне страниц для печати.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` для извлечения начальный номер страницы в диапазоне страниц для печати.  
  
### <a name="example"></a>Пример  
  В примере показано [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="getportname"></a>CPrintDialog::GetPortName  
 Получает имя текущего выбранного порта.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя выбранного порта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) для извлечения имени выбранного порта.  
  
### <a name="example"></a>Пример  
  В примере показано [CPrintDialog::GetDeviceName](#getdevicename).  
  
##  <a name="getprinterdc"></a>CPrintDialog::GetPrinterDC  
 Возвращает дескриптор контекста устройства принтера.  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор контекста устройства принтера в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если `bPrintSetupOnly` параметр `CPrintDialog` конструктор был **FALSE** (что означает, что отображается диалоговое окно печати), затем `GetPrinterDC` возвращает дескриптор контекста устройства, принтера. Необходимо вызвать Windows [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) функции для удаления контекста устройства, после завершения его использования.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#109;](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]  
  
##  <a name="gettopage"></a>CPrintDialog::GetToPage  
 Получает конечную страницу диапазон печати.  
  
```  
int GetToPage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Конечный номер страницы в диапазоне страниц для печати.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` для извлечения конечный номер страницы в диапазон страниц для печати.  
  
### <a name="example"></a>Пример  
  В примере показано [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="m_pd"></a>CPrintDialog::m_pd  
 Структуры, члены которого хранения характеристики объекта диалогового окна.  
  
```  
PRINTDLG& m_pd;  
```  
  
### <a name="remarks"></a>Примечания  
 После построения `CPrintDialog` объекта, можно использовать `m_pd` для задания различных аспектов диалоговым окном перед вызовом метода [DoModal](#domodal) функции-члена. Дополнительные сведения о `m_pd` структуры см. в разделе [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Если изменить `m_pd` член данных напрямую, переопределяют любое поведение по умолчанию.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#111;](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]  
  
##  <a name="printall"></a>CPrintDialog::PrintAll  
 Определяет, следует ли печатать все страницы документа.  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если все страницы в документе для печати; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` для определения необходимости печать всех страниц в документе.  
  
### <a name="example"></a>Пример  
  В примере показано [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="printcollate"></a>CPrintDialog::PrintCollate  
 Определяет ли упорядоченную запросу копии.  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь выбирает флажок collate в диалоговом окне. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` для определения, следует ли принтер collate все напечатанные копии документа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#110;](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]  
  
##  <a name="printrange"></a>CPrintDialog::PrintRange  
 Определяет, следует ли печать указанного диапазона страниц.  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если только диапазон страниц в документе для печати; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` для определения необходимости печать диапазона страниц в документе.  
  
### <a name="example"></a>Пример  
  В примере показано [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="printselection"></a>CPrintDialog::PrintSelection  
 Определяет, следует ли печатать только выбранные элементы.  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если только выбранные элементы для печати; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` для определения необходимости печати только выбранных элементов.  
  
### <a name="example"></a>Пример  
  В примере показано [CPrintDialog::m_pd](#m_pd).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC DIBLOOK](../../visual-cpp-samples.md)   
 [Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CPrintInfo-структура](../../mfc/reference/cprintinfo-structure.md)

