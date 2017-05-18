---
title: "Класс CPageSetupDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- page setup
- Print Setup dialog box
- Page Setup dialog box
- OLE Page Setup dialog box
- CPageSetupDialog class
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
caps.latest.revision: 24
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
ms.openlocfilehash: 81d36b3a005a291aca4c77dc9771a4fe92c304ee
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cpagesetupdialog-class"></a>Класс CPageSetupDialog
Инкапсулирует службы, предоставляемые стандартным диалоговым окном OLE "Параметры страницы" Windows с дополнительной поддержкой установки и изменения полей печати.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPageSetupDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)|Создает объект `CPageSetupDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|Создает контекст устройства для печати.|  
|[CPageSetupDialog::DoModal](#domodal)|Отображает диалоговое окно и позволяет пользователю сделать выбор.|  
|[CPageSetupDialog::GetDeviceName](#getdevicename)|Возвращает имя устройства принтера.|  
|[CPageSetupDialog::GetDevMode](#getdevmode)|Возвращает текущий `DEVMODE` принтера.|  
|[CPageSetupDialog::GetDriverName](#getdrivername)|Возвращает драйвер принтера.|  
|[CPageSetupDialog::GetMargins](#getmargins)|Возвращает текущие параметры полей принтера.|  
|[CPageSetupDialog::GetPaperSize](#getpapersize)|Возвращает размер бумаги принтера.|  
|[CPageSetupDialog::GetPortName](#getportname)|Возвращает имя порта вывода.|  
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|Вызывается платформой для подготовки к просмотру изображение экрана на печатной странице.|  
|[CPageSetupDialog::PreDrawPage](#predrawpage)|Вызывается средой перед отображением изображение экрана на печатной странице.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPageSetupDialog::m_psd](#m_psd)|Структура, используемая для настройки `CPageSetupDialog` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предназначен для вместо диалогового окна Настройка печати.  
  
 Для использования `CPageSetupDialog` объекта, сначала создайте объект с помощью `CPageSetupDialog` конструктор. После конструирования диалоговом окне можно задать или изменить значения в `m_psd` элемент данных для инициализации значений элементов управления диалогового окна. [M_psd](#m_psd) структуры имеет тип **PAGESETUPDLG**.  
  
 После инициализации диалоговыми окнами, вызовите `DoModal` функции-члена для отображения диалогового окна и разрешить пользователю выбирать параметры печати. `DoModal`Возвращает, выбрал ли пользователь ОК ( **IDOK**) или Отмена ( **IDCANCEL**) кнопки.  
  
 Если `DoModal` возвращает **IDOK**, можно использовать несколько `CPageSetupDialog`в функциях-членах или доступа `m_psd` члена данных, чтобы получить данные, введенные пользователем.  
  
> [!NOTE]
>  После закрытия стандартным диалоговым окном OLE страницы установки, любые изменения, внесенные пользователем, не сохраняются платформой. Возлагается само приложение, чтобы сохранить все значения в этом окне в постоянную папку, например члена класса в документ приложения или приложения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPageSetupDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdlgs.h  
  
##  <a name="cpagesetupdialog"></a>CPageSetupDialog::CPageSetupDialog  
 Эта функция вызывается для создания `CPageSetupDialog` объекта.  
  
```  
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна. Значения могут объединяться с помощью оператора побитового или. Эти значения имеют следующий смысл:  
  
- **PSD_DEFAULTMINMARGINS** задает Минимальная ширина, допустимый для поля страницы должен совпадать с принтера минимальных значений. Этот флаг учитывается, если **PSD_MARGINS** и **PSD_MINMARGINS** указаны флаги.  
  
- **PSD_INWININIINTLMEASURE** не реализован.  
  
- **PSD_MINMARGINS** заставляет систему используйте значения, указанные в **rtMinMargin** член как Минимальная допустимая ширина слева, сверху, справа и нижнего полей. Система не позволяет пользователю ввести шириной не меньше заданного минимального. Если **PSD_MINMARGINS** не указан, система задает Минимальная допустимая ширина допускаемым принтером.  
  
- **PSD_MARGINS** активирует элемент управления поля.  
  
- **PSD_INTHOUSANDTHSOFINCHES** вызывает единицы диалогового окна для измеряться в 1/1000 дюйма.  
  
- **PSD_INHUNDREDTHSOFMILLIMETERS** вызывает единицы диалогового окна для измеряться в 1/100 миллиметра.  
  
- **PSD_DISABLEMARGINS** отключает margin диалоговыми окнами.  
  
- **PSD_DISABLEPRINTER** отключает кнопку принтера.  
  
- **PSD_NOWARNING** запрещает отображение когда принтер по умолчанию не предупреждающее сообщение.  
  
- **PSD_DISABLEORIENTATION** отключает элемент управления диалогового окна ориентацию страницы.  
  
- **PSD_RETURNDEFAULT** вызывает `CPageSetupDialog` для возврата [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) и [DEVNAMES](../../mfc/reference/devnames-structure.md) структуры, которые инициализируются для на принтере по умолчанию без отображения диалоговое окно. Предполагается, что оба **hDevNames** и **hDevMode** , **NULL**; в противном случае, функция возвращает ошибку. Если старый драйвер принтера (более ранних, чем Windows версии 3.0), поддерживаемый на принтере по умолчанию только **hDevNames** возвращается; **hDevMode** is **NULL**.  
  
- **PSD_DISABLEPAPER** отключает элемент управления выбора бумаги.  
  
- **PSD_SHOWHELP** Отображение диалогового окна для отображения кнопки справки. **HwndOwner** члена не должно быть **NULL** Если этот флажок установлен.  
  
- **PSD_ENABLEPAGESETUPHOOK** позволяет функция обработчика, указанного в **lpfnSetupHook**.  
  
- **PSD_ENABLEPAGESETUPTEMPLATE** вынуждает операционную систему для создания диалогового окна, используя диалоговое окно «шаблон», определяется **hInstance** и **lpSetupTemplateName**.  
  
- **PSD_ENABLEPAGESETUPTEMPLATEHANDLE** указывает, что **hInstance** определяет блок данных, содержащий шаблон предварительно диалогового окна. Система пропускает **lpSetupTemplateName** Если этот флажок установлен.  
  
- **PSD_ENABLEPAGEPAINTHOOK** позволяет функция обработчика, указанного в **lpfnPagePaintHook**.  
  
- **PSD_DISABLEPAGEPAINTING** отключает области рисования диалогового окна.  
  
 `pParentWnd`  
 Указатель на родительский или владельца диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Используйте [DoModal](../../mfc/reference/cdialog-class.md#domodal) функцию, чтобы открыть диалоговое окно.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#94;](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>CPageSetupDialog::CreatePrinterDC  
 Создает контекст устройства принтера из [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) и [DEVNAMES](../../mfc/reference/devnames-structure.md) структуры.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор контекста устройства (DC), созданного принтера.  
  
##  <a name="domodal"></a>CPageSetupDialog::DoModal  
 Эта функция вызывается для отображения диалогового окна Windows Общие параметры OLE страницы и разрешить пользователю выбирать различные варианты настройки печати, например поля печати, размер и ориентация бумаги и принтер назначения.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **IDOK** или **IDCANCEL**. Если **IDCANCEL** будет возвращен, вызовите Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) функцию, чтобы определить, произошла ли ошибка.  
  
 **IDOK** и **IDCANCEL** константы, которые указывают, выбрал ли пользователь кнопку OK или "Отмена".  
  
### <a name="remarks"></a>Примечания  
 Кроме того пользователь может получить доступ к параметры принтера, например сетевого расположения и свойства, относящиеся к выбранному принтеру.  
  
 Если требуется инициализировать различных параметров диалогового окна Параметры страницы, задав члены `m_psd` структуры, следует сделать это до вызова `DoModal`, и после создания объекта диалогового окна. После вызова метода `DoModal`, вызывать другой член функции для получения параметров или данные, введенные пользователем в диалоговом окне.  
  
 Если требуется передать текущие параметры, введенные пользователем, позвонить [CWinApp::SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter). Эта функция берет информацию из `CPageSetupDialog` объекта и инициализирует и выбирает нового принтера контроллера домена с правильными атрибутами.  
  
 [!code-cpp[NVC_MFCDocView&#95;](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]  
  
### <a name="example"></a>Пример  
  В примере показано [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).  
  
##  <a name="getdevicename"></a>CPageSetupDialog::GetDeviceName  
 Вызывайте эту функцию после `DoModal` для извлечения имени выбранного принтера.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя устройства, используемые **CPageSetupDialog** объекта.  
  
##  <a name="getdevmode"></a>CPageSetupDialog::GetDevMode  
 Эта функция вызывается после вызова метода `DoModal` для получения информации о контексте устройства принтера `CPageSetupDialog` объекта.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) структуру данных, которая содержит сведения об инициализации устройства и среде драйвер принтера. Необходимо разблокировать память, занимаемую структурой с Windows [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) функции, который описан в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdrivername"></a>CPageSetupDialog::GetDriverName  
 Эта функция вызывается после вызова метода [DoModal](../../mfc/reference/cprintdialog-class.md#domodal) получить имя драйвера принтера, определяемые системой.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `CString` Указание имени драйвера, определяемые системой.  
  
### <a name="remarks"></a>Примечания  
 Использование указателя для `CString` объект, возвращаемый `GetDriverName` в качестве значения `lpszDriverName` в вызове [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="getmargins"></a>CPageSetupDialog::GetMargins  
 Эта функция вызывается после вызова метода `DoModal` для извлечения полей драйвера принтера.  
  
```  
void GetMargins(
    LPRECT lpRectMargins,  
    LPRECT lpRectMinMargins) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *lpRectMargins*  
 Указатель на [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) , описывающий (в дюймах 1/1000 или 1/100 мм) поля печати для выбранного принтера. Передайте **NULL** для этого параметра, если вы не заинтересованы в этот прямоугольник.  
  
 *lpRectMinMargins*  
 Указатель на `RECT` структуры или `CRect` объект, описывающий (в дюймах 1/1000 или 1/100 мм) минимальные поля печати для выбранного принтера. Передайте **NULL** для этого параметра, если вы не заинтересованы в этот прямоугольник.  
  
##  <a name="getpapersize"></a>CPageSetupDialog::GetPaperSize  
 Эта функция вызывается для получения размера бумаги, выбранного для печати.  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) объект, содержащий размер бумаги (в дюймах 1/1000 или 1/100 мм), выбранные для печати.  
  
##  <a name="getportname"></a>CPageSetupDialog::GetPortName  
 Эта функция вызывается после вызова метода `DoModal` для извлечения имени выбранного порта.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя выбранного порта.  
  
##  <a name="m_psd"></a>CPageSetupDialog::m_psd  
 Структура типа **PAGESETUPDLG**, члены которого хранения характеристики объекта диалогового окна.  
  
```  
PAGESETUPDLG m_psd;  
```  
  
### <a name="remarks"></a>Примечания  
 После построения `CPageSetupDialog` объекта, можно использовать `m_psd` для задания различных аспектов диалоговым окном перед вызовом метода `DoModal` функции-члена.  
  
 Если изменить `m_psd` член данных напрямую, переопределяют любое поведение по умолчанию.  
  
 Дополнительные сведения о [PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842) структуры см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 В примере показано [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).  
  
##  <a name="ondrawpage"></a>CPageSetupDialog::OnDrawPage  
 Вызывается платформой для рисования изображение экрана на печатной странице.  
  
```  
virtual UINT OnDrawPage(
    CDC* pDC,  
    UINT nMessage,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства принтера.  
  
 `nMessage`  
 Задает сообщение, указывающее область страницы, которые в настоящее время рисования. Ниже указаны доступные значения.  
  
- **WM_PSD_FULLPAGERECT** область всей страницы.  
  
- **WM_PSD_MINMARGINRECT** текущей минимальный размер полей.  
  
- **WM_PSD_MARGINRECT** текущего поля.  
  
- **WM_PSD_GREEKTEXTRECT** содержимого страницы.  
  
- **WM_PSD_ENVSTAMPRECT** область, выделенная для представления почтовой марки.  
  
- **WM_PSD_YAFULLPAGERECT** область для представления обратный адрес. В этой области расширяет по границам области пример страницы.  
  
 `lpRect`  
 Указатель на [CRect](../../atl-mfc-shared/reference/crect-class.md) или [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us) объект, содержащий координаты области рисования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если обработанное; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это изображение отображается как часть стандартным диалоговым окном OLE страницы программы установки. Реализация по умолчанию Рисует изображение страницы текста.  
  
 Переопределите эту функцию для настройки прорисовки определенной области изображения или всего изображения. Это можно сделать с помощью `switch` инструкции с **случае** инструкции проверки значения `nMessage`. Например для настройки отображения содержимого изображения страницы, можно использовать следующий код:  
  
 [!code-cpp[NVC_MFCDocView&#96;](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]  
  
 Обратите внимание, не нужно обработать каждый случай из `nMessage`. Можно обрабатывать один компонент изображения, несколько компонентов изображения или всю область.  
  
##  <a name="predrawpage"></a>CPageSetupDialog::PreDrawPage  
 Вызывается средой перед рисованием изображения экрана на печатной странице.  
  
```  
virtual UINT PreDrawPage(
    WORD wPaper,  
    WORD wFlags,  
    LPPAGESETUPDLG pPSD);
```  
  
### <a name="parameters"></a>Параметры  
 *wPaper*  
 Задает значение, указывающее размер бумаги. Это значение может быть одним из **DMPAPER_** значений, перечисленных в описании [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) структуры.  
  
 `wFlags`  
 Указывает ориентацию бумаги или конверта, и является ли принтер матричные или HPPCL (язык управления принтера Hewlett Packard) устройства. Этот параметр может принимать одно из следующих значений:  
  
-   0x001 бумаги в альбомной ориентации (матричный)  
  
-   0x003 бумаги в альбомной ориентации (HPPCL)  
  
-   0x005 бумаги в портретной ориентации (матричный)  
  
-   0x007 бумаги в портретной ориентации (HPPCL)  
  
-   0x00b конверта в альбомной ориентации (HPPCL)  
  
-   0x00d конверта в портретной ориентации (матричный)  
  
-   0x019 конверта в альбомной ориентации (матричный)  
  
-   0x01f конверта в портретной ориентации (матричный)  
  
 `pPSD`  
 Указатель на **PAGESETUPDLG** структуры. Дополнительные сведения о [PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842), в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если обработанное; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки прорисовки изображения. Если переопределить эту функцию и вернуть **TRUE**, необходимо нарисовать всего изображения. Если переопределить эту функцию и вернуть **FALSE**, рисуется изображение по умолчанию целиком платформой.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC WORDPAD](../../visual-cpp-samples.md)   
 [Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




