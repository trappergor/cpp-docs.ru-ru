---
title: "Класс CPrintDialogEx | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- Print Setup dialog box
- CPrintDialogEx class
- Print dialog box
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8dc8f01eef42b54af18ed07520d547768c931748
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cprintdialogex-class"></a>Класс CPrintDialogEx
Инкапсулирует службы, предоставляемые вкладкой свойств "Печать" в Windows 2000.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPrintDialogEx : public CCommonDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|Создает объект `CPrintDialogEx`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|Создает контекст устройства принтера без отображения диалогового окна печати.|  
|[CPrintDialogEx::DoModal](#domodal)|Открытие диалогового окна и дает пользователю возможность выбора.|  
|[CPrintDialogEx::GetCopies](#getcopies)|Получает количество запрошенных копий.|  
|[CPrintDialogEx::GetDefaults](#getdefaults)|Возвращает параметры устройства без Отображение диалогового окна.|  
|[CPrintDialogEx::GetDeviceName](#getdevicename)|Получает имя текущего выбранного принтера.|  
|[CPrintDialogEx::GetDevMode](#getdevmode)|Извлекает `DEVMODE` структуры.|  
|[CPrintDialogEx::GetDriverName](#getdrivername)|Получает имя драйвера принтера, определяемые системой.|  
|[CPrintDialogEx::GetPortName](#getportname)|Получает имя текущего выбранного порта.|  
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Возвращает дескриптор контекста устройства принтера.|  
|[CPrintDialogEx::PrintAll](#printall)|Определяет, следует ли печатать все страницы документа.|  
|[CPrintDialogEx::PrintCollate](#printcollate)|Определяет ли упорядоченную запросу копии.|  
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|Определяет, следует ли печать текущей страницы документа.|  
|[CPrintDialogEx::PrintRange](#printrange)|Определяет, следует ли печать указанного диапазона страниц.|  
|[CPrintDialogEx::PrintSelection](#printselection)|Определяет, следует ли печатать только выбранные элементы.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPrintDialogEx::m_pdex](#m_pdex)|Структура, используемая для настройки `CPrintDialogEx` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Можно положиться на платформе заниматься многими аспектами процесса печати для вашего приложения. Дополнительные сведения об использовании платформы для обработки заданий печати см. в статье [печати](../../mfc/printing.md).  
  
 Если требуется, чтобы приложение для обработки печати без участия framework, можно использовать `CPrintDialogEx` класса «как есть» с помощью конструктора, предоставленного или наследовании классов диалоговых окон с `CPrintDialogEx` и создание конструктора в соответствии с потребностями. В любом случае эти диалоговые будет работать как стандартные диалоговые окна MFC, поскольку они являются производными от класса `CCommonDialog`.  
  
 Для использования `CPrintDialogEx` объекта, сначала создайте объект с помощью `CPrintDialogEx` конструктор. После конструирования диалоговом окне можно задать или изменить какое-либо значение [m_pdex](#m_pdex) структуры для инициализации значений элементов управления диалогового окна. `m_pdex` Структуры имеет тип [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844). Дополнительные сведения о структуре см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Если не указать дескрипторов в `m_pdex` для **hDevMode** и **hDevNames** членов, необходимо вызвать функцию Windows **GlobalFree** для этих маркеров, после завершения работы с диалоговым окном.  
  
 После инициализации диалоговыми окнами, вызовите `DoModal` функции-члена для отображения диалогового окна и разрешить пользователю выбирать параметры печати. Если `DoModal` возвращает, можно определить, является ли пользователь выбрал кнопку OK, применить или "Отмена".  
  
 Если пользователь нажал кнопку "ОК", можно использовать `CPrintDialogEx`функции-члены для извлечения информации, введенное пользователем.  
  
 `CPrintDialogEx::GetDefaults` Для получения текущего значения по умолчанию принтер без отображения диалогового полезна функция-член. Этот метод не требует вмешательства пользователя.  
  
 Можно использовать окна **CommDlgExtendedError** функции, чтобы определить, произошла ли ошибка во время инициализации диалогового окна и для получения дополнительных сведений об ошибке. Дополнительные сведения об этой функции см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения об использовании `CPrintDialogEx`, в разделе [классы общих диалоговых окон](../../mfc/common-dialog-classes.md).  
  
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
  
##  <a name="cprintdialogex"></a>CPrintDialogEx::CPrintDialogEx  
 Создает окно свойств печати Windows 2000.  
  
```  
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна, объединенные с помощью побитового оператора OR. Например **PD_ALLPAGES** флаг задает диапазон печати по умолчанию для всех страниц документа. В разделе [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения об этих флагов.  
  
 `pParentWnd`  
 Указатель на окне родительский или владельца диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член только создает объект. Используйте `DoModal` функции-члена для отображения диалогового окна.  
  
##  <a name="createprinterdc"></a>CPrintDialogEx::CreatePrinterDC  
 Создает контекст устройства принтера (DC) из [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) и [DEVNAMES](../../mfc/reference/devnames-structure.md) структуры.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор контекста устройства, созданный принтера.  
  
### <a name="remarks"></a>Примечания  
 Возвращенный контроллер домена также хранятся в **hDC** членом [m_pdex](#m_pdex).  
  
 Предполагается, что этот контроллер домена является текущий принтер DC и любые другие ранее полученные принтер, контроллеры доменов должны быть удалены. Эту функцию можно вызывать и использовать полученный контроллера домена без постоянно отображать диалоговое окно печати.  
  
##  <a name="domodal"></a>CPrintDialogEx::DoModal  
 Эта функция вызывается для отображения страницы свойств общих печати Windows 2000 и разрешить пользователю выбирать различные параметры печати, такие как число копий, диапазон страниц и ли должно быть по копиям.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 INT_PTR возвращаемое значение — на самом деле значение HRESULT. В разделе значения возврата в [PrintDlgEx](http://msdn.microsoft.com/library/windows/desktop/ms646942) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать параметры диалогового окна печати, задав члены `m_pdex` структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 После вызова метода `DoModal`, можно вызвать другой член функции для получения параметров или данные, введенные пользователем в диалоговом окне.  
  
 Если **PD_RETURNDC** флаг используется при вызове `DoModal`, принтер контроллера домена будут возвращены в **hDC** членом [m_pdex](#m_pdex). Этот контроллер домена должен быть освобожден с помощью вызова [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) вызывающим объектом `CPrintDialogEx`.  
  
##  <a name="getcopies"></a>CPrintDialogEx::GetCopies  
 Эта функция вызывается после вызова метода `DoModal` для получения количества копий запрошено.  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число копий, в запросе.  
  
##  <a name="getdefaults"></a>CPrintDialogEx::GetDefaults  
 Эта функция используется для получения значения по умолчанию устройства принтера по умолчанию без отображения диалоговое окно.  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** в случае успешного выполнения, в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Создает контекст устройства принтера (DC) из [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) и [DEVNAMES](../../mfc/reference/devnames-structure.md) структуры.  
  
 `GetDefaults`Отображает окно свойств печати. Вместо этого он задает **hDevNames** и **hDevMode** члены [m_pdex](#m_pdex) на дескрипторы для [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) и [DEVNAMES](../../mfc/reference/devnames-structure.md) структуры, которые инициализируются для на принтере по умолчанию. Оба **hDevNames** и **hDevMode** должен иметь значение NULL, или `GetDefaults` завершается ошибкой.  
  
 Если **PD_RETURNDC** флаг установлен, эта функция не только возвращает **hDevNames** и **hDevMode** (находится в **m_pdex.hDevNames** и **m_pdex.hDevMode**), вызывающей стороне, но возвратит принтера контроллера домена в **m_pdex.hDC**. Отвечает вызывающего объекта, чтобы удалить принтер DC и вызвать Windows [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) функция дескрипторах при завершении работы с `CPrintDialogEx` объекта.  
  
##  <a name="getdevicename"></a>CPrintDialogEx::GetDeviceName  
 Эта функция вызывается после вызова метода [DoModal](#domodal) для извлечения имени выбранного принтера или после вызова метода [GetDefaults](#getdefaults) для извлечения имени принтера по умолчанию.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя выбранного принтера.  
  
### <a name="remarks"></a>Примечания  
 Использование указателя для `CString` объект, возвращаемый `GetDeviceName` в качестве значения `lpszDeviceName` в вызове [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="getdevmode"></a>CPrintDialogEx::GetDevMode  
 Эта функция вызывается после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) для получения сведений об устройстве печати.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) структуру данных, которая содержит сведения об инициализации устройства и среде драйвер принтера. Необходимо разблокировать память, занимаемую структурой с Windows [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) функции, который описан в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdrivername"></a>CPrintDialogEx::GetDriverName  
 Эта функция вызывается после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) получить имя драйвера принтера, определяемые системой.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `CString` Указание имени драйвера, определяемые системой.  
  
### <a name="remarks"></a>Примечания  
 Использование указателя для `CString` объект, возвращаемый `GetDriverName` в качестве значения `lpszDriverName` в вызове [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="getportname"></a>CPrintDialogEx::GetPortName  
 Эта функция вызывается после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) для извлечения имени выбранного порта.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя выбранного порта.  
  
##  <a name="getprinterdc"></a>CPrintDialogEx::GetPrinterDC  
 Возвращает дескриптор контекста устройства, принтера.  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор контекста устройства принтера.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать Windows [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) функции для удаления контекста устройства, после завершения его использования.  
  
##  <a name="m_pdex"></a>CPrintDialogEx::m_pdex  
 Структура PRINTDLGEX, члены которого хранения характеристики объекта диалогового окна.  
  
```  
PRINTDLGEX m_pdex;  
```  
  
### <a name="remarks"></a>Примечания  
 После построения `CPrintDialogEx` объекта, можно использовать `m_pdex` для задания различных аспектов диалоговым окном перед вызовом метода [DoModal](#domodal) функции-члена. Дополнительные сведения о `m_pdex` структуры см. в разделе [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Если изменить `m_pdex` член данных напрямую, переопределяют любое поведение по умолчанию.  
  
##  <a name="printall"></a>CPrintDialogEx::PrintAll  
 Эта функция вызывается после вызова метода `DoModal` для определения необходимости печать всех страниц в документе.  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** печатных; в противном случае если все страницы в документе **FALSE**.  
  
##  <a name="printcollate"></a>CPrintDialogEx::PrintCollate  
 Эта функция вызывается после вызова метода `DoModal` для определения, следует ли принтер collate все напечатанные копии документа.  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** , если пользователь выбирает флажок collate в диалоговом окне; в противном случае **FALSE**.  
  
##  <a name="printcurrentpage"></a>CPrintDialogEx::PrintCurrentPage  
 Эта функция вызывается после вызова метода `DoModal` для определения необходимости распечатать текущую страницу в документе.  
  
```  
BOOL PrintCurrentPage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если **Печать текущей страницы** выбран в диалоговом окне печати; в противном случае **FALSE**.  
  
##  <a name="printrange"></a>CPrintDialogEx::PrintRange  
 Эта функция вызывается после вызова метода `DoModal` для определения необходимости печать диапазона страниц в документе.  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** если только диапазон страниц в документе печатных; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Можно определить диапазоны указанную страницу из [m_pdex](#m_pdex) (см. **nPageRanges**, **nMaxPageRanges**, и **lpPageRanges** в [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]).  
  
##  <a name="printselection"></a>CPrintDialogEx::PrintSelection  
 Эта функция вызывается после вызова метода `DoModal` для определения необходимости печати только выбранных элементов.  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** если только выбранные элементы печатных; в противном случае **FALSE**.  
  
## <a name="see-also"></a>См. также  
 [Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CPrintInfo-структура](../../mfc/reference/cprintinfo-structure.md)

