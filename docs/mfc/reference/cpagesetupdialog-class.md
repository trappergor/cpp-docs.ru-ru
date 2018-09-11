---
title: Класс CPageSetupDialog | Документация Майкрософт
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
ms.openlocfilehash: c134d2e1dc6f3782446afc57b8384279a615e86f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197461"
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
|[CPageSetupDialog::DoModal](#domodal)|Отображает диалоговое окно и позволяет пользователю сделать выбор.|  
|[CPageSetupDialog::GetDeviceName](#getdevicename)|Возвращает имя устройства принтера.|  
|[CPageSetupDialog::GetDevMode](#getdevmode)|Возвращает текущий DEVMODE принтера.|  
|[CPageSetupDialog::GetDriverName](#getdrivername)|Возвращает драйвер принтера.|  
|[CPageSetupDialog::GetMargins](#getmargins)|Возвращает текущие параметры полей принтера.|  
|[CPageSetupDialog::GetPaperSize](#getpapersize)|Возвращает размер бумаги принтера.|  
|[CPageSetupDialog::GetPortName](#getportname)|Возвращает имя порта вывода.|  
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|Вызывается платформой для отрисовки экранного рисунка или напечатанной страницы.|  
|[CPageSetupDialog::PreDrawPage](#predrawpage)|Вызывается до отрисовки экранного рисунка или напечатанной страницы.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPageSetupDialog::m_psd](#m_psd)|Структура, используемая для настройки `CPageSetupDialog` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предназначен вместо диалогового окна Параметры печати.  
  
 Чтобы использовать `CPageSetupDialog` следует сначала создать объект с помощью `CPageSetupDialog` конструктор. После создания диалоговом окне можно задать или изменить значения в `m_psd` данные-член для инициализации значений элементов управления диалогового окна. [M_psd](#m_psd) структуры имеет тип PAGESETUPDLG.  
  
 После инициализации элементов окна, вызовите `DoModal` функция-член отображается диалоговое окно и позволяет пользователю выбрать параметры печати. `DoModal` Возвращает, является ли пользователь выбрал кнопку ОК (IDOK) или Отмена (IDCANCEL).  
  
 Если `DoModal` возвращает IDOK, можно использовать несколько `CPageSetupDialog`в функциях-членах или доступа `m_psd` извлекаемого элемента данных, данные, введенные пользователем.  
  
> [!NOTE]
>  После закрытия общее диалоговое окно Параметры OLE страницы, любые изменения, внесенные пользователем, не будут сохранены платформой. Возлагается само приложение, чтобы сохранить все значения в этом диалоговом окне в постоянную папку, например члена класса документа приложения или приложения.  
  
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
 Вызывайте эту функцию для создания `CPageSetupDialog` объекта.  
  
```  
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *dwFlags*  
 Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна. Значения могут объединяться с помощью битового оператора или. Эти значения имеют следующий смысл:  
  
- PSD_DEFAULTMINMARGINS задает Минимальная допустимая ширина для поля страницы должен совпадать с минимальных значений принтера. Этот флаг учитывается, если также указаны флаги PSD_MARGINS и PSD_MINMARGINS.  
  
- PSD_INWININIINTLMEASURE не реализован.  
  
- PSD_MINMARGINS заставляет систему для использования значения, указанные в `rtMinMargin` член как Минимальная допустимая ширина для слева, сверху, справа и нижнего полей. Система запрещает пользователю ввести, ширина которого меньше заданного минимального. Если PSD_MINMARGINS не указан, система устанавливает минимальных значений ширины допустимый допускаемым языком принтера.  
  
- PSD_MARGINS активирует область элемента управления поля.  
  
- PSD_INTHOUSANDTHSOFINCHES вызывает единицы измерения 1/1000 дюйма диалоговое окно.  
  
- PSD_INHUNDREDTHSOFMILLIMETERS вызывает диалоговое окно единицы измерения 1/100 миллиметра.  
  
- PSD_DISABLEMARGINS отключает элементам управления диалоговыми полей.  
  
- PSD_DISABLEPRINTER отключает "принтер".  
  
- PSD_NOWARNING предотвращает предупреждающее сообщение отображаемое при принтер по умолчанию.  
  
- PSD_DISABLEORIENTATION отключает элемент управления диалогового окна ориентации страницы.  
  
- Вызывает PSD_RETURNDEFAULT `CPageSetupDialog` для возврата [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) и [DEVNAMES](../../mfc/reference/devnames-structure.md) структур, которые были инициализированы для на принтере по умолчанию без отображения диалоговое окно. Предполагается, что оба `hDevNames` и `hDevMode` имеют значение NULL; в противном случае функция возвращает ошибку. Если на принтере по умолчанию поддерживается старый драйвер принтера (более ранних, чем Windows версии 3.0), только `hDevNames` возвращается; `hDevMode` имеет значение NULL.  
  
- PSD_DISABLEPAPER отключает элемент управления для выбора бумаги.  
  
- PSD_SHOWHELP вызывает диалоговое окно, чтобы показать кнопку "Справка". `hwndOwner` Член не должен иметь значение NULL, если этот флаг задан.  
  
- PSD_ENABLEPAGESETUPHOOK позволяет функция-обработчик указан в `lpfnSetupHook`.  
  
- PSD_ENABLEPAGESETUPTEMPLATE вынуждает операционную систему для создания диалоговом окне, используя диалоговое окно «шаблон», идентифицируемый `hInstance` и `lpSetupTemplateName`.  
  
- Указывает, что PSD_ENABLEPAGESETUPTEMPLATEHANDLE `hInstance` определяет блок данных, содержащий шаблон предварительно загруженных диалогового окна. Система игнорирует `lpSetupTemplateName` Если этот флаг задан.  
  
- PSD_ENABLEPAGEPAINTHOOK позволяет функция-обработчик указан в `lpfnPagePaintHook`.  
  
- PSD_DISABLEPAGEPAINTING отключает области рисования диалогового окна.  
  
 *pParentWnd*  
 Указатель на родительский объект или владельца диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Используйте [DoModal](../../mfc/reference/cdialog-class.md#domodal) функцию, чтобы открыть диалоговое окно.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>  CPageSetupDialog::CreatePrinterDC  
 Создает контекст устройства принтера из [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) и [DEVNAMES](../../mfc/reference/devnames-structure.md) структуры.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор контекста устройства только что созданный принтера (DC).  
  
##  <a name="domodal"></a>  CPageSetupDialog::DoModal  
 Вызывайте эту функцию для отображается диалоговое окно Общие параметры OLE страницы Windows и позволяет пользователю выбрать различные варианты настройки печати, например границы печати, размер и ориентацию бумаги и принтер назначения.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 IDOK и IDCANCEL. Если возвращается IDCANCEL, вызовите Windows [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) функцию, чтобы определить, произошла ли ошибка.  
  
 IDOK и IDCANCEL являются константы, указывающие, является ли пользователь выбрал кнопку ОК или "Отмена".  
  
### <a name="remarks"></a>Примечания  
 Кроме того пользователь может получить доступ к параметры принтера, такие как сетевое расположение и свойства, относящиеся к выбранному принтеру.  
  
 Если вы хотите инициализировать различные параметры диалогового окна Параметры страницы путем определения участников `m_psd` структуры, это следует сделать до вызова метода `DoModal`, и после создания объекта диалогового окна. После вызова метода `DoModal`, вызывать другой член функции для получения параметров или данные, введенные пользователем в диалоговом окне.  
  
 Если вы хотите распространить текущие параметры, введенные пользователем, вызова с [CWinApp::SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter). Эта функция принимает сведения из `CPageSetupDialog` объекта и инициализирует и служит для выбора принтера новый контроллер домена с верными атрибутами.  
  
 [!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]  
  
### <a name="example"></a>Пример  
  См. в примере [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).  
  
##  <a name="getdevicename"></a>  CPageSetupDialog::GetDeviceName  
 Вызывайте эту функцию после `DoModal` для получения названия для выбранного принтера.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя устройства, используемые `CPageSetupDialog` объекта.  
  
##  <a name="getdevmode"></a>  CPageSetupDialog::GetDevMode  
 Вызывайте эту функцию после вызова метода `DoModal` для получения сведений о контексте устройства принтера `CPageSetupDialog` объекта.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) структуру данных, которая содержит сведения об инициализации устройства и среду драйвер принтера. Чтобы разблокировать память, занимаемую эту структуру с Windows [GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock) функции, который описан в пакете Windows SDK.  
  
##  <a name="getdrivername"></a>  CPageSetupDialog::GetDriverName  
 Вызывайте эту функцию после вызова метода [DoModal](../../mfc/reference/cprintdialog-class.md#domodal) получить имя драйвер принтера, определенная системой.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` Указание имени драйвера, определенная системой.  
  
### <a name="remarks"></a>Примечания  
 Использование указателя на `CString` объект, возвращаемый `GetDriverName` для параметра `lpszDriverName` в вызове [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="getmargins"></a>  CPageSetupDialog::GetMargins  
 Вызывайте эту функцию после вызова `DoModal` для извлечения полей драйвер принтера.  
  
```  
void GetMargins(
    LPRECT lpRectMargins,  
    LPRECT lpRectMinMargins) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *lpRectMargins*  
 Указатель на [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) , описывающий (в дюймах 1/1000 или 1/100 мм) поля печати для выбранного принтера. Передайте NULL для этого параметра, если вы не заинтересованы в этот прямоугольник.  
  
 *lpRectMinMargins*  
 Указатель на `RECT` структуры или `CRect` , описывающий (в дюймах 1/1000 или 1/100 мм) минимальный размер полей печати для выбранного принтера. Передайте NULL для этого параметра, если вы не заинтересованы в этот прямоугольник.  
  
##  <a name="getpapersize"></a>  CPageSetupDialog::GetPaperSize  
 Вызывайте эту функцию для определения размера бумаги, выбранного для печати.  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) объект, содержащий размер бумаги (в дюймах 1/1000 или 1/100 мм), выбранные для печати.  
  
##  <a name="getportname"></a>  CPageSetupDialog::GetPortName  
 Вызывайте эту функцию после вызова метода `DoModal` получить имя порта текущий выбранный принтер.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя порта текущий выбранный принтер.  
  
##  <a name="m_psd"></a>  CPageSetupDialog::m_psd  
 Структура типа PAGESETUPDLG, члены которой хранения характеристики объекта диалогового окна.  
  
```  
PAGESETUPDLG m_psd;  
```  
  
### <a name="remarks"></a>Примечания  
 После построения `CPageSetupDialog` объекта, можно использовать `m_psd` для задания различных аспектов диалоговом окне перед вызовом `DoModal` функция-член.  
  
 При изменении `m_psd` элемент данных напрямую, переопределяет любое поведение по умолчанию.  
  
 Дополнительные сведения о [PAGESETUPDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpsda) структуры, см. в Windows SDK.  
  
 См. в примере [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).  
  
##  <a name="ondrawpage"></a>  CPageSetupDialog::OnDrawPage  
 Вызывается платформой для отрисовки экранного рисунка или напечатанной страницы.  
  
```  
virtual UINT OnDrawPage(
    CDC* pDC,  
    UINT nMessage,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 *основного контроллера домена*  
 Указатель на контекст устройства принтера.  
  
 *nMessage*  
 Указывает сообщение, область страницы, в настоящее время отрисовывается. Ниже указаны доступные значения.  
  
- WM_PSD_FULLPAGERECT области всей страницы.  
  
- WM_PSD_MINMARGINRECT текущий минимальный размер полей.  
  
- WM_PSD_MARGINRECT текущего поля.  
  
- WM_PSD_GREEKTEXTRECT содержимое страницы.  
  
- Область WM_PSD_ENVSTAMPRECT, выделенная для представления почтовой марки.  
  
- Область WM_PSD_YAFULLPAGERECT представление обратный адрес. Эта область распространяется на краю области страницы примера.  
  
 *lpRect*  
 Указатель на [CRect](../../atl-mfc-shared/reference/crect-class.md) или [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us) объект, содержащий координаты области рисования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если обработан; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Этот образ затем отображается как часть общее диалоговое окно Параметры OLE страницы. Реализация по умолчанию Рисует изображение страницы текста.  
  
 Переопределите эту функцию для настройки прорисовки в определенную область изображения, или все изображение. Это можно сделать с помощью **переключения** инструкции с **случай** инструкции проверки значения *nMessage*. Например чтобы изменить параметры отрисовки содержимого изображения страницы, можно использовать в следующем примере кода:  
  
 [!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]  
  
 Обратите внимание, что не нужно каждый случай *nMessage*. Вы можете обрабатывать один компонент изображения, несколько компонентов, изображения или всю область.  
  
##  <a name="predrawpage"></a>  CPageSetupDialog::PreDrawPage  
 Вызвано структурой перед рисованием экранного рисунка или напечатанной страницы.  
  
```  
virtual UINT PreDrawPage(
    WORD wPaper,  
    WORD wFlags,  
    LPPAGESETUPDLG pPSD);
```  
  
### <a name="parameters"></a>Параметры  
 *wPaper*  
 Задает значение, указывающее размер бумаги. Это значение может принимать одно из **DMPAPER_** значений, перечисленных в описании [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) структуры.  
  
 *wFlags*  
 Указывает ориентацию бумаги или конверта, и является ли принтер матричный или ориентации для HPPCLHPPCL (язык управления принтера Hewlett Packard) устройство. Этот параметр может принимать одно из следующих значений:  
  
-   0x001 бумаги в альбомном режиме (матричного)  
  
-   0x003 бумаги в альбомном режиме (ориентации для HPPCLHPPCL)  
  
-   0x005 бумаги в книжной ориентации (матричного)  
  
-   0x007 бумаги в книжной ориентации (ориентации для HPPCLHPPCL)  
  
-   0x00b конверт в режиме альбомной (ориентации для HPPCLHPPCL)  
  
-   0x00d конверт в режиме книжной (матричного)  
  
-   0x019 конверт в режиме альбомной (матричного)  
  
-   0x01f конверт в режиме книжной (матричного)  
  
 *pPSD*  
 Указатель на структуру `PAGESETUPDLG`. Дополнительные сведения о [PAGESETUPDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpsda), см. в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если обработан; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки прорисовки изображения. Если вы переопределите эту функцию и возвращает значение TRUE, необходимо рисовать все изображение. Если вы переопределите эту функцию и возвращает значение FALSE, платформой рисуется изображение по умолчанию целиком.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC WORDPAD](../../visual-cpp-samples.md)   
 [Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



