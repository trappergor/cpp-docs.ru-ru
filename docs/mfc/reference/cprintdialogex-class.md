---
title: "Класс CPrintDialogEx | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
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
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 147a3d638f76f291a9732b340335331730f5b74d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cprintdialogex-class"></a>Класс CPrintDialogEx
Инкапсулирует службы, предоставляемые вкладкой свойств "Печать" в Windows 2000.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPrintDialogEx : public CCommonDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|Создает объект `CPrintDialogEx`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|Создает контекст устройства принтера без отображения диалогового окна печати.|  
|[CPrintDialogEx::DoModal](#domodal)|Отображает диалоговое окно и дает пользователю возможность выбора.|  
|[CPrintDialogEx::GetCopies](#getcopies)|Возвращает число копий запрошено.|  
|[CPrintDialogEx::GetDefaults](#getdefaults)|Получает значения по умолчанию устройства не отображение диалогового окна.|  
|[CPrintDialogEx::GetDeviceName](#getdevicename)|Извлекает имя выбранного принтера.|  
|[CPrintDialogEx::GetDevMode](#getdevmode)|Извлекает `DEVMODE` структуры.|  
|[CPrintDialogEx::GetDriverName](#getdrivername)|Извлекает имя драйвер принтера, определенная системой.|  
|[CPrintDialogEx::GetPortName](#getportname)|Извлекает имя выбранного порта.|  
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Получает дескриптор контекста устройства принтера.|  
|[CPrintDialogEx::PrintAll](#printall)|Определяет, следует ли печати всех страниц документа.|  
|[CPrintDialogEx::PrintCollate](#printcollate)|Определяет ли сопоставить запрашиваются копий.|  
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|Определяет необходимость Печать текущей страницы документа.|  
|[CPrintDialogEx::PrintRange](#printrange)|Определяет, следует ли печать указанного диапазона страниц.|  
|[CPrintDialogEx::PrintSelection](#printselection)|Определяет, следует ли печати только выбранные элементы.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPrintDialogEx::m_pdex](#m_pdex)|Структура, используемая для настройки `CPrintDialogEx` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Можно положиться на платформе, чтобы обрабатывать различные аспекты процесс печати для вашего приложения. Дополнительные сведения об использовании платформы для обработки заданий печати см. в статье [печати](../../mfc/printing.md).  
  
 Если требуется приложению обрабатывать печать без участия платформы, можно использовать `CPrintDialogEx` класса «как есть» с помощью конструктора, предоставленного или наследовании классов диалоговых окон из `CPrintDialogEx` и создание конструктора в соответствии с потребностями. В любом случае эти диалоговые будет работать как стандартные диалоговые окна MFC, так как они являются производными от класса `CCommonDialog`.  
  
 Для использования `CPrintDialogEx` объекта, сначала создайте объект с помощью `CPrintDialogEx` конструктор. После создания диалоговом окне можно задать или изменить значения в [m_pdex](#m_pdex) структуры для инициализации значений элементов управления в диалоговое окно «». `m_pdex` Структуры имеет тип [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844). Дополнительные сведения о структуре см. в Windows SDK.  
  
 Если не указать дескрипторов в `m_pdex` для **hDevMode** и **hDevNames** членов, нужно убедиться, что вызов функции Windows **GlobalFree** для этих маркеров Когда вы закончите с диалоговым окном.  
  
 После инициализации элементы управления диалоговых окон, вызовите метод `DoModal` функции-члена для отображения диалогового окна и разрешить пользователю выбирать параметры печати. Если `DoModal` возвращает, можно определить, является ли пользователь выбрал кнопку ОК, применить или "Отмена".  
  
 Если нажата кнопка ОК, можно использовать `CPrintDialogEx`в функции-члены для извлечения информации, введенное пользователем.  
  
 `CPrintDialogEx::GetDefaults` Функция-член эффективно для получения текущего значения по умолчанию принтер без отображения диалоговое окно. Этот метод не требует вмешательства пользователя.  
  
 Можно использовать окна **CommDlgExtendedError** функции, чтобы определить, произошла ли ошибка во время инициализации диалогового окна и Дополнительные сведения об ошибке. Дополнительные сведения о данной функции см. в Windows SDK.  
  
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
 Создает таблицу свойств печати Windows 2000.  
  
```  
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна, объединенные с помощью оператора побитового или Например **PD_ALLPAGES** флаг задает диапазон печати по умолчанию для всех страниц документа. В разделе [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) структуры в Windows SDK, Дополнительные сведения об этих флагов.  
  
 `pParentWnd`  
 Указатель на диалоговое окно родительского или владельца.  
  
### <a name="remarks"></a>Примечания  
 Только эта функция-член создает объект. Используйте `DoModal` функции-члена для отображения диалогового окна.  
  
##  <a name="createprinterdc"></a>CPrintDialogEx::CreatePrinterDC  
 Создает контекст устройства принтера (DC) из [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) и [DEVNAMES](../../mfc/reference/devnames-structure.md) структуры.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор контекста устройства только что созданный принтера.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый контроллера домена также сохраняются в **hDC** членом [m_pdex](#m_pdex).  
  
 Предполагается, что этот контроллер домена является текущей принтера и любые другие ранее получены принтер, контроллеры домена должны быть удалены. Эту функцию можно вызывать и использовать полученный контроллера домена без когда-либо отображения диалогового окна печати.  
  
##  <a name="domodal"></a>CPrintDialogEx::DoModal  
 Эта функция вызывается для отображения страницы свойств общих печати Windows 2000 и разрешить пользователю выбирать различные параметры печати, например число копий, диапазон страниц и ли должно быть по копиям.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 INT_PTR возвращаемое значение — фактически значение HRESULT. В разделе возвращают значения в [PrintDlgEx](http://msdn.microsoft.com/library/windows/desktop/ms646942) в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные параметры диалогового окна печати, задав члены `m_pdex` структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 После вызова метода `DoModal`, можно вызывать другой член функции для получения параметров или данные, введенные пользователем в диалоговом окне.  
  
 Если **PD_RETURNDC** флаг используется при вызове `DoModal`, будут возвращены принтера **hDC** членом [m_pdex](#m_pdex). Этот контроллер домена необходимо освободить с помощью вызова [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) вызывающим объектом `CPrintDialogEx`.  
  
##  <a name="getcopies"></a>CPrintDialogEx::GetCopies  
 Эта функция вызывается после вызова метода `DoModal` для получения количества сохраняемых копий запрошено.  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число копий, в запросе.  
  
##  <a name="getdefaults"></a>CPrintDialogEx::GetDefaults  
 Вызывайте эту функцию для получения значения по умолчанию устройства принтера по умолчанию без отображения диалоговое окно.  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** в случае успеха, в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Создает контекст устройства принтера (DC) из [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) и [DEVNAMES](../../mfc/reference/devnames-structure.md) структуры.  
  
 `GetDefaults`не отображать окно свойств печати. Вместо этого он задает **hDevNames** и **hDevMode** члены [m_pdex](#m_pdex) дескрипторам [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) и [DEVNAMES ](../../mfc/reference/devnames-structure.md) структуры, которые инициализируются для на принтере по умолчанию. Оба **hDevNames** и **hDevMode** должен иметь значение NULL, или `GetDefaults` завершается ошибкой.  
  
 Если **PD_RETURNDC** флаг установлен, эта функция не вернет только **hDevNames** и **hDevMode** (расположенный в **m_pdex.hDevNames** и **m_pdex.hDevMode**) вызывающему объекту, но также возвращает принтера в **m_pdex.hDC**. Отвечает вызывающего объекта, чтобы удалить принтер контроллера домена, а вызовите Windows [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) функция дескрипторах при завершении работы с `CPrintDialogEx` объекта.  
  
##  <a name="getdevicename"></a>CPrintDialogEx::GetDeviceName  
 Эта функция вызывается после вызова метода [DoModal](#domodal) для извлечения имени выбранного принтера или после вызова метода [GetDefaults](#getdefaults) для извлечения имени принтера по умолчанию.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя выбранного принтера.  
  
### <a name="remarks"></a>Примечания  
 Используйте указатель `CString` объект, возвращаемый `GetDeviceName` в качестве значения `lpszDeviceName` при обращении к [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="getdevmode"></a>CPrintDialogEx::GetDevMode  
 Эта функция вызывается после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) для получения сведений об устройстве печати.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) структуру данных, которая содержит сведения об инициализации устройства и среду драйвер принтера. Необходимо разблокировать память, занимаемую эту структуру с Windows [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) функции, которая описана в Windows SDK.  
  
##  <a name="getdrivername"></a>CPrintDialogEx::GetDriverName  
 Эта функция вызывается после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) получить имя драйвер принтера, определенная системой.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` Указание имени драйвера, определенная системой.  
  
### <a name="remarks"></a>Примечания  
 Используйте указатель `CString` объект, возвращаемый `GetDriverName` в качестве значения `lpszDriverName` при обращении к [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="getportname"></a>CPrintDialogEx::GetPortName  
 Эта функция вызывается после вызова метода [DoModal](#domodal) или [GetDefaults](#getdefaults) для извлечения имени выбранного порта.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя порта выбранного принтера.  
  
##  <a name="getprinterdc"></a>CPrintDialogEx::GetPrinterDC  
 Возвращает дескриптор контекста устройства принтера.  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор контекста устройства принтера.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать Windows [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) , позволяющей удалить контекст устройства после завершения его использования.  
  
##  <a name="m_pdex"></a>CPrintDialogEx::m_pdex  
 Структура PRINTDLGEX, члены которого хранения характеристики объекта диалогового окна.  
  
```  
PRINTDLGEX m_pdex;  
```  
  
### <a name="remarks"></a>Примечания  
 После построения `CPrintDialogEx` объекта, можно использовать `m_pdex` для задания различных аспектов диалоговым окном перед вызовом [DoModal](#domodal) функции-члена. Дополнительные сведения о `m_pdex` структуры см. в разделе [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) в Windows SDK.  
  
 При изменении `m_pdex` член данных напрямую, будут переопределяться любой по умолчанию.  
  
##  <a name="printall"></a>CPrintDialogEx::PrintAll  
 Эта функция вызывается после вызова метода `DoModal` для определения необходимости печать всех страниц в документе.  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** печатного; в противном случае если все страницы в документе **FALSE**.  
  
##  <a name="printcollate"></a>CPrintDialogEx::PrintCollate  
 Эта функция вызывается после вызова метода `DoModal` для определения, следует ли принтер collate все печатные копии документа.  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если пользователь выбирает флажок collate в диалоговом окне; в противном случае **FALSE**.  
  
##  <a name="printcurrentpage"></a>CPrintDialogEx::PrintCurrentPage  
 Эта функция вызывается после вызова метода `DoModal` для определения необходимости Печать текущей страницы документа.  
  
```  
BOOL PrintCurrentPage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если **Печать текущей страницы** выбранных в диалоговом окне печати; в противном случае **FALSE**.  
  
##  <a name="printrange"></a>CPrintDialogEx::PrintRange  
 Эта функция вызывается после вызова метода `DoModal` для определения необходимости напечатать диапазон страниц в документе.  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** если только диапазон страниц в документе печати; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Можно определить диапазоны указанную страницу из [m_pdex](#m_pdex) (см. **nPageRanges**, **nMaxPageRanges**, и **lpPageRanges** в [ PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) структуры в Windows SDK).  
  
##  <a name="printselection"></a>CPrintDialogEx::PrintSelection  
 Эта функция вызывается после вызова метода `DoModal` для определения необходимости печать только выбранных элементов.  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** если только выбранные элементы печати; в противном случае **FALSE**.  
  
## <a name="see-also"></a>См. также  
 [Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Структура CPrintInfo](../../mfc/reference/cprintinfo-structure.md)
