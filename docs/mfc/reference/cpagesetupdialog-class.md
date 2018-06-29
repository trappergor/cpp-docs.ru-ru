---
title: Класс CPageSetupDialog | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPageSetupDialog
- AFXDLGS/CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CreatePrinterDC
- AFXDLGS/CPageSetupDialog::DoModal
- AFXDLGS/CPageSetupDialog::GetDeviceName
- AFXDLGS/CPageSetupDialog::GetDevMode
- AFXDLGS/CPageSetupDialog::GetDriverName
- AFXDLGS/CPageSetupDialog::GetMargins
- AFXDLGS/CPageSetupDialog::GetPaperSize
- AFXDLGS/CPageSetupDialog::GetPortName
- AFXDLGS/CPageSetupDialog::OnDrawPage
- AFXDLGS/CPageSetupDialog::PreDrawPage
- AFXDLGS/CPageSetupDialog::m_psd
dev_langs:
- C++
helpviewer_keywords:
- CPageSetupDialog [MFC], CPageSetupDialog
- CPageSetupDialog [MFC], CreatePrinterDC
- CPageSetupDialog [MFC], DoModal
- CPageSetupDialog [MFC], GetDeviceName
- CPageSetupDialog [MFC], GetDevMode
- CPageSetupDialog [MFC], GetDriverName
- CPageSetupDialog [MFC], GetMargins
- CPageSetupDialog [MFC], GetPaperSize
- CPageSetupDialog [MFC], GetPortName
- CPageSetupDialog [MFC], OnDrawPage
- CPageSetupDialog [MFC], PreDrawPage
- CPageSetupDialog [MFC], m_psd
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd96f0240f8dd97fdda54fd2d00231db14ae3d47
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079187"
---
# <a name="cpagesetupdialog-class"></a>Класс CPageSetupDialog
Инкапсулирует службы, предоставляемые стандартным диалоговым окном OLE "Параметры страницы" Windows с дополнительной поддержкой установки и изменения полей печати.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPageSetupDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)|Создает объект `CPageSetupDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|Создает контекст устройства для печати.|  
|[CPageSetupDialog::DoModal](#domodal)|Отображает диалоговое окно и выбирать создания пользователя.|  
|[CPageSetupDialog::GetDeviceName](#getdevicename)|Возвращает имя устройства принтера.|  
|[CPageSetupDialog::GetDevMode](#getdevmode)|Возвращает текущий `DEVMODE` принтера.|  
|[CPageSetupDialog::GetDriverName](#getdrivername)|Возвращает драйвер принтера.|  
|[CPageSetupDialog::GetMargins](#getmargins)|Возвращает текущие параметры полей принтера.|  
|[CPageSetupDialog::GetPaperSize](#getpapersize)|Возвращает размер бумаги для принтера.|  
|[CPageSetupDialog::GetPortName](#getportname)|Возвращает имя выходной порт.|  
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|Вызывается платформой для отрисовки экранного рисунка или напечатанной страницы.|  
|[CPageSetupDialog::PreDrawPage](#predrawpage)|Вызывается платформой до отрисовки экранного рисунка или напечатанной страницы.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPageSetupDialog::m_psd](#m_psd)|Структура, используемая для настройки `CPageSetupDialog` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предназначен для вместо диалогового окна "Настройка печати".  
  
 Для использования `CPageSetupDialog` объекта, сначала создайте объект с помощью `CPageSetupDialog` конструктор. После создания диалоговом окне можно задать или изменить значения в `m_psd` элемент данных для инициализации значений элементов управления в диалоговое окно «». [M_psd](#m_psd) структуры имеет тип **PAGESETUPDLG**.  
  
 После инициализации элементы управления диалоговых окон, вызовите метод `DoModal` функции-члена для отображения диалогового окна и разрешить пользователю выбирать параметры печати. `DoModal` Возвращает, является ли пользователь выбрал ОК ( **IDOK**) или "Отмена" ( **IDCANCEL**) кнопки.  
  
 Если `DoModal` возвращает **IDOK**, можно использовать несколько `CPageSetupDialog`в функциях-членах или доступа `m_psd` член данных, данные, введенные пользователем.  
  
> [!NOTE]
>  После закрытия стандартным диалоговым окном OLE страницы установки, любые изменения, внесенные пользователем, не сохраняются платформой. Именно само приложение, чтобы сохранить все значения в этом окне в постоянную папку, например члена класса документа приложения или приложения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPageSetupDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdlgs.h  
  
##  <a name="cpagesetupdialog"></a>  CPageSetupDialog::CPageSetupDialog  
 Эта функция вызывается для создания `CPageSetupDialog` объекта.  
  
```  
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *dwFlags*  
 Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна. Значения могут быть объединены с помощью оператора побитового или. Эти значения имеют следующий смысл:  
  
- **PSD_DEFAULTMINMARGINS** задает минимальной ширины допустимые для поля страницы должен совпадать с принтера минимальных значений. Этот флаг учитывается, если **PSD_MARGINS** и **PSD_MINMARGINS** указаны флаги.  
  
- **PSD_INWININIINTLMEASURE** не реализован.  
  
- **PSD_MINMARGINS** заставляет систему для использования значений, указанных в **rtMinMargin** элемент в качестве минимальной ширины допустимый для слева, сверху, справа и нижнего полей. Система пользователю вводить ширина которого меньше, чем заданное минимальное. Если **PSD_MINMARGINS** не указан, система устанавливает Минимальная допустимая ширина допускаемым языком принтера.  
  
- **PSD_MARGINS** активирует область элемента управления поля.  
  
- **PSD_INTHOUSANDTHSOFINCHES** вызывает единицы диалогового окна для измеряться в 1/1000 дюйма.  
  
- **PSD_INHUNDREDTHSOFMILLIMETERS** вызывает единицы диалогового окна для измеряться в 1/100 миллиметра.  
  
- **PSD_DISABLEMARGINS** отключает поле элементы управления диалоговых окон.  
  
- **PSD_DISABLEPRINTER** отключает кнопку ' принтер '.  
  
- **PSD_NOWARNING** препятствует отображению при принтер не по умолчанию предупреждающее сообщение.  
  
- **PSD_DISABLEORIENTATION** отключает элемент управления диалогового окна ориентацию страницы.  
  
- **PSD_RETURNDEFAULT** вызывает `CPageSetupDialog` для возврата [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) и [DEVNAMES](../../mfc/reference/devnames-structure.md) структуры, которые инициализируются для на принтере по умолчанию без отображения диалоговое окно. Предполагается, что оба **hDevNames** и **hDevMode** , **NULL**; в противном случае функция возвращает ошибку. Если старый драйвер принтера (более ранних, чем Windows версии 3.0), поддерживается на принтере по умолчанию только **hDevNames** возвращается; **hDevMode** — **NULL**.  
  
- **PSD_DISABLEPAPER** отключает элемент управления выбора бумаги.  
  
- **PSD_SHOWHELP** диалоговое окно для отображения кнопки справки. **HwndOwner** член не должен быть **NULL** Если задан этот флаг.  
  
- **PSD_ENABLEPAGESETUPHOOK** позволяет функция-обработчик, указанный в **lpfnSetupHook**.  
  
- **PSD_ENABLEPAGESETUPTEMPLATE** вынуждает операционную систему для создания диалогового окна с помощью шаблона окно определяется **hInstance** и **lpSetupTemplateName**.  
  
- **PSD_ENABLEPAGESETUPTEMPLATEHANDLE** указывает, что **hInstance** определяет блок данных, который содержит шаблон предварительно загруженных диалогового окна. Система игнорирует **lpSetupTemplateName** Если задан этот флаг.  
  
- **PSD_ENABLEPAGEPAINTHOOK** позволяет функция-обработчик, указанный в **lpfnPagePaintHook**.  
  
- **PSD_DISABLEPAGEPAINTING** отключает области рисования диалогового окна.  
  
 *pParentWnd*  
 Указатель на родительский или владелец диалоговое окно «».  
  
### <a name="remarks"></a>Примечания  
 Используйте [DoModal](../../mfc/reference/cdialog-class.md#domodal) функцию, чтобы открыть диалоговое окно.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>  CPageSetupDialog::CreatePrinterDC  
 Создает контекст устройства принтера из [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) и [DEVNAMES](../../mfc/reference/devnames-structure.md) структуры.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор контекста устройства только что созданный принтера (DC).  
  
##  <a name="domodal"></a>  CPageSetupDialog::DoModal  
 Эта функция вызывается для отображения диалогового окна Windows Общие параметры OLE страницы и разрешить пользователю выбирать различные варианты настройки печати, таких как границы печати, размер и ориентацию бумаги и назначения принтера.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **IDOK** или **IDCANCEL**. Если **IDCANCEL** будет возвращен, вызовите Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) функцию, чтобы определить, произошла ли ошибка.  
  
 **IDOK** и **IDCANCEL** — константы, которые указывают, является ли пользователь выбрал кнопку OK или "Отмена".  
  
### <a name="remarks"></a>Примечания  
 Кроме того он может использовать параметры программы установки принтера, такие как сетевое расположение и свойства, относящиеся к выбранному принтеру.  
  
 Если требуется инициализировать различные параметры диалогового окна Параметры страницы, задав члены `m_psd` структуры, это следует сделать до вызова метода `DoModal`, и после создания объекта диалогового окна. После вызова метода `DoModal`, вызывать функции для получения параметров или данные, введенные пользователем в диалоговом окне другого элемента.  
  
 Если требуется передать текущие параметры, введенные пользователем, вызвать [CWinApp::SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter). Эта функция принимает данные от `CPageSetupDialog` объекта и инициализирует и служит для выбора принтера нового контроллера домена с правильными атрибутами.  
  
 [!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).  
  
##  <a name="getdevicename"></a>  CPageSetupDialog::GetDeviceName  
 Вызывайте эту функцию после `DoModal` для извлечения имени выбранного принтера.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя устройства, используемые `CPageSetupDialog` объекта.  
  
##  <a name="getdevmode"></a>  CPageSetupDialog::GetDevMode  
 Эта функция вызывается после вызова метода `DoModal` для получения сведений о контексте устройства принтера `CPageSetupDialog` объекта.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) структуру данных, которая содержит сведения об инициализации устройства и среду драйвер принтера. Необходимо разблокировать память, занимаемую эту структуру с Windows [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) функции, которая описана в Windows SDK.  
  
##  <a name="getdrivername"></a>  CPageSetupDialog::GetDriverName  
 Эта функция вызывается после вызова метода [DoModal](../../mfc/reference/cprintdialog-class.md#domodal) получить имя драйвер принтера, определенная системой.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` Указание имени драйвера, определенная системой.  
  
### <a name="remarks"></a>Примечания  
 Используйте указатель `CString` объект, возвращаемый `GetDriverName` в качестве значения `lpszDriverName` при обращении к [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="getmargins"></a>  CPageSetupDialog::GetMargins  
 Эта функция вызывается после вызова `DoModal` для извлечения полей драйвер принтера.  
  
```  
void GetMargins(
    LPRECT lpRectMargins,  
    LPRECT lpRectMinMargins) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *lpRectMargins*  
 Указатель на [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) , описывающий (в дюймах 1/1000 или 1/100 мм) поля печати для выбранного принтера. Передайте **NULL** для этого параметра, если вы не заинтересованы в этот прямоугольник.  
  
 *lpRectMinMargins*  
 Указатель на `RECT` структуры или `CRect` объекта, который описывает минимальные поля печати для выбранного принтера, (в дюймах 1/1000 или 1/100 мм). Передайте **NULL** для этого параметра, если вы не заинтересованы в этот прямоугольник.  
  
##  <a name="getpapersize"></a>  CPageSetupDialog::GetPaperSize  
 Эта функция вызывается для определения размера бумаги, выбранного для печати.  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) объект, содержащий размер бумаги (в дюймах 1/1000 или 1/100 мм), выбранные для печати.  
  
##  <a name="getportname"></a>  CPageSetupDialog::GetPortName  
 Эта функция вызывается после вызова метода `DoModal` для извлечения имени выбранного порта.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя порта выбранного принтера.  
  
##  <a name="m_psd"></a>  CPageSetupDialog::m_psd  
 Структура типа **PAGESETUPDLG**, члены которого хранения характеристики объекта диалогового окна.  
  
```  
PAGESETUPDLG m_psd;  
```  
  
### <a name="remarks"></a>Примечания  
 После построения `CPageSetupDialog` объекта, можно использовать `m_psd` для задания различных аспектов диалоговым окном перед вызовом `DoModal` функции-члена.  
  
 При изменении `m_psd` член данных напрямую, будут переопределяться любой по умолчанию.  
  
 Дополнительные сведения о [PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842) структуры см. в разделе Windows SDK.  
  
 Далее приведен пример [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).  
  
##  <a name="ondrawpage"></a>  CPageSetupDialog::OnDrawPage  
 Вызывается платформой для отрисовки экранного рисунка или напечатанной страницы.  
  
```  
virtual UINT OnDrawPage(
    CDC* pDC,  
    UINT nMessage,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 *контроллер домена*  
 Указатель на контекст устройства принтера.  
  
 *nMessage*  
 Указывает сообщение, показывающее, область страницы, в которых выводится в настоящее время. Ниже указаны доступные значения.  
  
- **WM_PSD_FULLPAGERECT** области всей страницы.  
  
- **WM_PSD_MINMARGINRECT** текущей минимальный размер полей.  
  
- **WM_PSD_MARGINRECT** текущего поля.  
  
- **WM_PSD_GREEKTEXTRECT** содержимое страницы.  
  
- **WM_PSD_ENVSTAMPRECT** область, выделенная для марки представления.  
  
- **WM_PSD_YAFULLPAGERECT** область для представления обратный адрес. В этой области расширяет по границам страницы область «образец».  
  
 *lpRect*  
 Указатель на [CRect](../../atl-mfc-shared/reference/crect-class.md) или [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us) объект, содержащий координаты области рисования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если обработанное; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это изображение отображается как часть стандартным диалоговым окном OLE страницы программы установки. Реализация по умолчанию выводит изображение страницы текста.  
  
 Переопределите эту функцию для настройки прорисовки определенной области изображения или всего изображения. Это можно сделать с помощью **переключения** инструкции с **случай** инструкций, обращаясь к значению *nMessage*. Например чтобы изменить параметры отрисовки содержимого изображения страницы, можно использовать в следующем примере кода:  
  
 [!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]  
  
 Обратите внимание, что не нужно каждый случай *nMessage*. Вы можете обрабатывать один компонент изображения несколько компонентов изображения или всю область.  
  
##  <a name="predrawpage"></a>  CPageSetupDialog::PreDrawPage  
 Вызывается платформой перед рисованием экранного рисунка или напечатанной страницы.  
  
```  
virtual UINT PreDrawPage(
    WORD wPaper,  
    WORD wFlags,  
    LPPAGESETUPDLG pPSD);
```  
  
### <a name="parameters"></a>Параметры  
 *wPaper*  
 Задает значение, указывающее размер бумаги. Это значение может быть одним из **DMPAPER_** значений, перечисленных в описании [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) структуры.  
  
 *wFlags*  
 Указывает ориентацию бумаги или конверта, и является ли принтер матричный или HPPCL (язык управления принтера Hewlett Packard) устройства. Этот параметр может принимать одно из следующих значений:  
  
-   0x001 бумаги в альбомной ориентации (матричного)  
  
-   0x003 бумаги в альбомной ориентации (HPPCL)  
  
-   0x005 бумаги в книжной ориентации (матричного)  
  
-   0x007 бумаги в книжной ориентации (HPPCL)  
  
-   0x00b конверта в альбомной ориентации (HPPCL)  
  
-   0x00d конверт в режиме книжной ориентации (матричного)  
  
-   0x019 конверта в альбомной ориентации (матричного)  
  
-   0x01f конверт в режиме книжной ориентации (матричного)  
  
 *pPSD*  
 Указатель на **PAGESETUPDLG** структуры. Дополнительные сведения о [PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842), см. в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если обработанное; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки прорисовки изображения. Если переопределить эту функцию и вернуть **TRUE**, необходимо нарисовать все изображение. Если переопределить эту функцию и вернуть **FALSE**, рисуется изображение по умолчанию целиком платформой.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC WORDPAD](../../visual-cpp-samples.md)   
 [Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



