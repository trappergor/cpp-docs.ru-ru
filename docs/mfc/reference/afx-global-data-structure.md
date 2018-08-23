---
title: Структура AFX_GLOBAL_DATA | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFX_GLOBAL_DATA
dev_langs:
- C++
helpviewer_keywords:
- AFX_GLOBAL_DATA structure [MFC]
- AFX_GLOBAL_DATA constructor
ms.assetid: c7abf2fb-ad5e-4336-a01d-260c29ed53a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9df970022ccc4f358864c3e3462ffea2b373cd00
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2018
ms.locfileid: "42541508"
---
# <a name="afxglobaldata-structure"></a>AFX_GLOBAL_DATA - структура
Структура `AFX_GLOBAL_DATA` содержит поля и методы, используемые для управления платформой или настройки внешнего вида и поведения приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct AFX_GLOBAL_DATA  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`|Создает структуру `AFX_GLOBAL_DATA` .|  
|`AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::Cleanup](#cleanup)|Освобождает ресурсы, выделенные платформой, например кисти, шрифты и библиотеки DLL.|  
|[AFX_GLOBAL_DATA::D2D1MakeRotateMatrix](#d2d1makerotatematrix)|Создает преобразование вращения, осуществляющее поворот на указанный угол вокруг указанной точки.|  
|[AFX_GLOBAL_DATA::DrawParentBackground](#drawparentbackground)|Рисует фон родительского объекта элемента управления в заданной области.|  
|[AFX_GLOBAL_DATA::DrawTextOnGlass](#drawtextonglass)|Рисует заданный текст в визуальном стиле указанной темы.|  
|[AFX_GLOBAL_DATA::ExcludeTag](#excludetag)|Удаляет заданную пару тегов XML из указанного буфера.|  
|[AFX_GLOBAL_DATA::GetColor](#getcolor)|Получает текущий цвет из указанного элемента пользовательского интерфейса.|  
|[AFX_GLOBAL_DATA::GetDirect2dFactory](#getdirect2dfactory)|Получает указатель на интерфейс `ID2D1Factory` , хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.|  
|[AFX_GLOBAL_DATA::GetHandCursor](#gethandcursor)|Извлекает стандартный курсор в виде руки, идентификатор которого равен `IDC_HAND`.|  
|[AFX_GLOBAL_DATA::GetITaskbarList](#getitaskbarlist)|Создает и сохраняет в глобальных данных указатель на интерфейс ITaskBarList.|  
|[AFX_GLOBAL_DATA::GetITaskbarList3](#getitaskbarlist3)|Создает и сохраняет в глобальных данных указатель на интерфейс ITaskBarList3.|  
|[AFX_GLOBAL_DATA::GetNonClientMetrics](#getnonclientmetrics)|Получает метрики, связанные с неклиентской областью несвернутого окна.|  
|[AFX_GLOBAL_DATA::GetShellAutohideBars](#getshellautohidebars)|Определяет положения автоматически скрываемых панелей оболочки.|  
|[AFX_GLOBAL_DATA::GetTextHeight](#gettextheight)|Получает высоту символов текста в текущем шрифте.|  
|[AFX_GLOBAL_DATA::GetWICFactory](#getwicfactory)|Получает указатель на интерфейс `IWICImagingFactory` , хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.|  
|[AFX_GLOBAL_DATA::GetWriteFactory](#getwritefactory)|Получает указатель на интерфейс `IDWriteFactory` , хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|Инициализирует фабрики `D2D`, `DirectWrite`и `WIC` . Данный метод следует вызывать до инициализации основного окна.|  
|[AFX_GLOBAL_DATA::Is32BitIcons](#is32biticons)|Указывает, поддерживаются ли стандартные 32-разрядные значки.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|Определяет, был ли инициализирован `D2D` .|  
|[AFX_GLOBAL_DATA::IsDwmCompositionEnabled](#isdwmcompositionenabled)|Предоставляет простой способ для вызова метода [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) Windows.|  
|[AFX_GLOBAL_DATA::IsHighContrastMode](#ishighcontrastmode)|Указывает, отображаются ли сейчас изображения с высокой контрастностью.|  
|[AFX_GLOBAL_DATA::OnSettingChange](#onsettingchange)|Определяет текущее состояние для анимации меню рабочего стола и функций автоматического скрытия панели задач.|  
|[AFX_GLOBAL_DATA::RegisterWindowClass](#registerwindowclass)|Регистрирует указанный класс окна MFC.|  
|[AFX_GLOBAL_DATA::ReleaseTaskBarRefs](#releasetaskbarrefs)|Освобождает интерфейсы, полученные через методы GetITaskbarList и GetITaskbarList3.|  
|[AFX_GLOBAL_DATA::Resume](#resume)|Повторно инициализирует Внутренние указатели функции, которые обращаются к методам, которые поддерживают Windows [темы и визуальные стили](/windows/desktop/Controls/visual-styles-overview).|  
|[AFX_GLOBAL_DATA::SetLayeredAttrib](#setlayeredattrib)|Предоставляет простой способ для вызова метода [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) Windows.|  
|[AFX_GLOBAL_DATA::SetMenuFont](#setmenufont)|Создает указанный логический шрифт.|  
|[AFX_GLOBAL_DATA::ShellCreateItemFromParsingName](#shellcreateitemfromparsingname)|Создает и инициализирует объект элемента оболочки из имени синтаксического анализа.|  
|[AFX_GLOBAL_DATA::UpdateFonts](#updatefonts)|Повторно инициализирует логические шрифты, используемые платформой.|  
|[AFX_GLOBAL_DATA::UpdateSysColors](#updatesyscolors)|Инициализирует цвета, глубину цвета, кисти, перья и изображения, используемые платформой.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport)|Включает или отключает поддержку Microsoft Active Accessibility. Active Accessibility предлагает надежные методы для предоставления информации об элементах пользовательского интерфейса.|  
|[AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport)|Указывает, включена ли поддержка Microsoft Active Accessibility.|  
|[AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable](#iswindowslayersupportavailable)|Указывает, поддерживает ли операционная система многослойные окна.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание:|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport](#bisosalphablendingsupport)|Указывает, поддерживает ли текущая операционная система альфа-смешение.|  
|[AFX_GLOBAL_DATA::bIsWindows7](#biswindows7)|Указывает, выполняется ли приложение в ОС Windows 7 или более поздней версии.|  
|[AFX_GLOBAL_DATA::clrActiveCaptionGradient](#clractivecaptiongradient)|Задает цвет градиента для активного заголовка. Обычно используется для закрепляемых панелей.|  
|[AFX_GLOBAL_DATA::clrInactiveCaptionGradient](#clrinactivecaptiongradient)|Задает цвет градиента для неактивного заголовка. Обычно используется для закрепляемых панелей.|  
|[AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons](#m_busebuiltin32biticons)|Указывает, использует ли платформа стандартные 32-разрядные цветные значки или значки более низкого разрешения.|  
|[AFX_GLOBAL_DATA::m_bUseSystemFont](#m_busesystemfont)|Указывает, используется ли системный шрифт для меню, панелей инструментов и лент.|  
|[AFX_GLOBAL_DATA::m_hcurHand](#m_hcurhand)|Сохраняет дескриптор курсора в виде ладони.|  
|[AFX_GLOBAL_DATA::m_hcurStretch](#m_hcurstretch)|Сохраняет дескриптор для курсора растяжения по горизонтали.|  
|[AFX_GLOBAL_DATA::m_hcurStretchVert](#m_hcurstretchvert)|Сохраняет дескриптор для курсора растяжения по вертикали.|  
|[AFX_GLOBAL_DATA::m_hiconTool](#m_hicontool)|Сохраняет дескриптор для значка средства.|  
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin](#m_nautohidetoolbarmargin)|Указывает смещение от самой левой автоматически скрываемой панели инструментов до левой части панели стыковки.|  
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing](#m_nautohidetoolbarspacing)|Указывает интервал между автоматически скрываемыми панелями инструментов.|  
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](#m_ndragframethicknessdock)|Указывает толщину кадра перетаскивания, который используется для взаимодействия в закрепленном состоянии.|  
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](#m_ndragframethicknessfloat)|Указывает толщину кадра перетаскивания, который используется для взаимодействия в плавающем состоянии.|  
  
### <a name="remarks"></a>Примечания  
 Большинство данных в структуре `AFX_GLOBAL_DATA` инициализируется при запуске приложения.  
  
### <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `AFX_GLOBAL_DATA`   
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxglobals.h  
  
### <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


## <a name="bisosalphablendingsupport"></a> AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport
Указывает, поддерживает ли операционная система альфа-смешение.  
  
  
```  
BOOL  bIsOSAlphaBlendingSupport;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение TRUE указывает, что поддерживается альфа-смешением; в противном случае — значение FALSE.  
  

## <a name="cleanup"></a> AFX_GLOBAL_DATA::Cleanup
Освобождает ресурсы, выделенные платформой, например кисти, шрифты и библиотеки DLL.  
  
  
```  
void CleanUp();
```  
## <a name="d2d1makerotatematrix"></a> AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
Создает преобразование вращения, осуществляющее поворот на указанный угол вокруг указанной точки.  
  
  
```  
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,  
    D2D1_POINT_2F center,  
    D2D1_MATRIX_3X2_F *matrix);
```  
  
### <a name="parameters"></a>Параметры   
 *угол*  
 Угол поворота по часовой стрелке в градусах.  
  
 *Center*  
 Точка, вокруг которой выполняется поворот.  
  
 *Матрица*  
 При возвращении данного метода содержит новый преобразование поворота. Для этого параметра необходимо выделить хранилище.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В противном случае возвращает значение S_OK, если успешно, или значение ошибки.  
  
## <a name="drawparentbackground"></a> AFX_GLOBAL_DATA::DrawParentBackground
Рисует фон родительского объекта элемента управления в заданной области.  
  
  
```  
BOOL DrawParentBackground(
    CWnd* pWnd,   
    CDC* pDC,   
    LPRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Параметры   
 [in] *pWnd*  
 Указатель на окно элемента управления.  
  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
 [in] *lpRect*  
 Указатель на прямоугольник, ограничивающий область для рисования. Значение по умолчанию имеет значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.  
  
## <a name="drawtextonglass"></a> AFX_GLOBAL_DATA::DrawTextOnGlass
Рисует заданный текст в визуальном стиле указанной темы.  
  
  
```  
BOOL DrawTextOnGlass(
    HTHEME hTheme,   
    CDC* pDC,   
    int iPartId,   
    int iStateId,   
    CString strText,   
    CRect rect,   
    DWORD dwFlags,   
    int nGlowSize = 0,   
    COLORREF clrText = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Параметры   
 [in] *hTheme*  
 Дескриптор данных темы окна или значение NULL. Платформа использует указанную тему для рисования текста, если этот параметр не является NULL, и поддерживаются темы. В противном случае платформа не использует тему для рисования текста.  
  
 Используйте [OpenThemeData](http://msdn.microsoft.com/library/windows/desktop/bb759821) метод для создания HTHEME.  
  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
 [in] *iPartId*  
 Часть элемента управления, имеющая нужный вид текста. Дополнительные сведения см. в столбце "Части" в таблице [Части и состояния](http://msdn.microsoft.com/library/windows/desktop/bb773210). Если это значение равно 0, текст рисуется с помощью шрифта по умолчанию или шрифта, выбранного в контексте устройства.  
  
 [in] *iStateId*  
 Состояние элемента управления, имеющее нужный вид текста. Дополнительные сведения см. в столбце "Состояния" в таблице [Части и состояния](http://msdn.microsoft.com/library/windows/desktop/bb773210).  
  
 [in] *strText*  
 Текст для отрисовки.  
  
 [in] *rect*  
 Границы области, в которой рисуется заданный текст.  
  
 [in] *dwFlags*  
 Побитовое сочетание (OR) флагов, определяющих способ рисования указанного текста.  
  
 Если *hTheme* параметр `NULL` или если темы не поддерживается и не включены, *nFormat* параметр [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) метод описывает допустимые флаги. Если темы поддерживаются, *dwFlags* параметр [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) Допустимые флаги описываются метод.  
  
 [in] *nGlowSize*  
 Размер эффекта свечения, рисуемого на фоне перед рисованием заданного текста. Значение по умолчанию — 0.  
  
 [in] *clrText*  
 Цвет рисования заданного текста. Значением по умолчанию является цвет по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если тема используется для рисования заданного текста; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Тема определяет визуальный стиль приложения. Тема не используется для рисования текста, если *hTheme* параметра равно NULL, или если [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) метод не поддерживается, или если [диспетчер окон рабочего стола](http://msdn.microsoft.com/library/windows/desktop/aa969540) композиции (DWM) отключен.  
  
### <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [Части и состояния](http://msdn.microsoft.com/library/windows/desktop/bb773210)   
 [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext)   
 [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317)   
 [Диспетчер окон рабочего стола](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [Включение и контроль композиции DWM](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="enableaccessibilitysupport"></a> AFX_GLOBAL_DATA::EnableAccessibilitySupport
Включает или отключает поддержку Microsoft Active Accessibility.  
  
  
```  
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры   
 [in] *bEnable*  
 Значение TRUE, чтобы включить поддержку специальных возможностей; Значение FALSE, чтобы отключить поддержку специальных возможностей. Значение по умолчанию — TRUE.  
  
### <a name="remarks"></a>Примечания  
 Active Accessibility — это технология, основанная на модели COM, которая улучшает программами и совместно продуктов поддержки специальных возможностей операционной системы Windows. Он предоставляет надежные методы для предоставления информации об элементах пользовательского интерфейса. Тем не менее доступна новая модель специальных возможностей, называется Microsoft UI Automation. Сравнение этих двух технологий, см. в разделе [модели автоматизации пользовательского интерфейса и Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility).  
  
 Используйте [AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport) метод, чтобы определить, включена ли поддержка Microsoft Active Accessibility.  
  
 
### <a name="see-also"></a>См. также  
 [Модели автоматизации пользовательского интерфейса и Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)   
 [AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport)

## <a name="excludetag"></a> AFX_GLOBAL_DATA::ExcludeTag
Удаляет заданную пару тегов XML из указанного буфера.  
  
  
```  
BOOL ExcludeTag(
    CString& strBuffer,  
    LPCTSTR lpszTag,  
    CString& strTag,  
    BOOL bIsCharsList = FALSE);
```  
  
### <a name="parameters"></a>Параметры   
 [in] *strBuffer*  
 Буфер текста.  
  
 [in] *lpszTag*  
 Имя пары открывающих и закрывающих тегов XML.  
  
 [out] *strTag*  
 При возвращении данного метода *strTag* параметр содержит текст, который находится между открывающим и закрывающим XML теги, которые имеют имена, *lpszTag* параметра. Любые начальные или конечные пробел удаляется из результата.  
  
 [in] *bIsCharsList*  
 Значение true, чтобы преобразовать символы для escape-символов в *strTag* параметр в фактических escape-символов; Значение FALSE, не для выполнения преобразования. Значение по умолчанию — FALSE. Дополнительные сведения см. в разделе "Замечания".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Пару тегов XML состоит из именованных открывающих и закрывающих тегов, которые указывают начало и конец цепочки текста в указанном буфере. *StrBuffer* параметр задает буфер и *lpszTag* параметр указывает имя XML-тегов.  
  
 Эти символы в следующей таблице можно используйте для кодирования набор escape-символы в указанном буфере. Укажите значение TRUE для *bIsCharsList* параметра для преобразования символов в *strTag* параметр в фактических escape-символы. В следующей таблице использует [_T()](../../c-runtime-library/data-type-mappings.md) макрос, указание файлов символов и escape-символ строки.  
  
|Символ|Escape-символ|  
|------------|----------------------|  
|_T ("\\\t")|_T("\t")|  
|_T ("\\\n")|_T("\n")|  
|_T ("\\\r")|_T("\r")|  
|_T ("\\\b")|_T("\b")|  
|_T("LT")|_T ("\<")|  
|_T("GT")|_T("&GT;")|  
|_T("AMP")|_T("&AMP;")|  
  
## <a name="getcolor"></a> AFX_GLOBAL_DATA::GetColor
Получает текущий цвет из указанного элемента пользовательского интерфейса.  
  
  
```  
COLORREF GetColor(int nColor);
```  
  
### <a name="parameters"></a>Параметры   
 [in] *nColor*  
 Значение, указывающее элемент пользовательского интерфейса, цвет которого извлекается. Список допустимых значений см. в разделе *nIndex* параметр [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение цвета RGB указанного элемента пользовательского интерфейса. Дополнительные сведения см. в разделе "Замечания".  
  
### <a name="remarks"></a>Примечания  
 Если *nColor* параметра выходит за пределы диапазона, возвращаемое значение равно нулю. Поскольку нуль также является допустимое значение RGB, нельзя использовать этот метод, чтобы определить, поддерживается ли текущая операционная система системного цвета. Вместо этого используйте [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927) метод, который возвращает значение NULL, если цвет не поддерживается.  
  
### <a name="see-also"></a>См. также  

 [Функция GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927)

## <a name="getdirect2dfactory"></a> AFX_GLOBAL_DATA::GetDirect2dFactory
 Возвращает указатель на интерфейс ID2D1Factory, хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.  
  
  
```  
ID2D1Factory* GetDirect2dFactory();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Factory при успешном создании фабрики, или значение NULL, если происходит сбой при создании или текущая операционная система отсутствует поддержка D2D.  
  
## <a name="gethandcursor"></a>  AFX_GLOBAL_DATA::GetHandCursor
Извлекает стандартный курсор, в виде руки, идентификатор которого равен IDC_HAND.  
  
  
```  
HCURSOR GetHandCursor();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор курсор в виде руки.  

## <a name="getnonclientmetrics"></a> AFX_GLOBAL_DATA::GetNonClientMetrics
Получает метрики, связанные с неклиентской областью несвернутого окна.  
  
  
```  
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```  
  
### <a name="parameters"></a>Параметры   
 [in, out] *info*  
 Объект [NONCLIENTMETRICS](http://msdn.microsoft.com/library/windows/desktop/ff729175) структуру, содержащую масштабируемой метрики, связанные с неклиентской области несвернутого окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.  
 
  
### <a name="see-also"></a>См. также   
 [Структура NONCLIENTMETRICS](http://msdn.microsoft.com/library/windows/desktop/ff729175)

## <a name="gettextheight"></a> AFX_GLOBAL_DATA::GetTextHeight
 Получает высоту символов текста в текущем шрифте.  
  
  
```  
int GetTextHeight(BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Параметры   
 [in] *bHorz*  
 Значение TRUE, чтобы получить высоту символов при текста по горизонтали; Значение FALSE, чтобы получить высоту символов, когда текст вертикально. Значение по умолчанию — TRUE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота элемента текущего шрифта, измеряется от его ascender до его подстрочный элемент символа.  
  
## <a name="getwicfactory"></a> AFX_GLOBAL_DATA::GetWICFactory
Возвращает указатель на интерфейс IWICImagingFactory, хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.  
  
  
```  
IWICImagingFactory* GetWICFactory();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IWICImagingFactory при успешном создании фабрики, или значение NULL, если происходит сбой при создании или текущая операционная система отсутствует поддержка WIC.  
  
## <a name="getwritefactory"></a> AFX_GLOBAL_DATA::GetWriteFactory
Возвращает указатель на интерфейс IDWriteFactory, хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.  
  
  
```  
IDWriteFactory* GetWriteFactory();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IDWriteFactory при успешном создании фабрики, или значение NULL, если происходит сбой при создании или текущая операционная система отсутствует поддержка DirectWrite.  
 
## <a name="initd2d"></a> AFX_GLOBAL_DATA::InitD2D
Инициализирует фабрики D2D, DirectWrite и WIC. Данный метод следует вызывать до инициализации основного окна.  
  
  
```  
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
### <a name="parameters"></a>Параметры   
 *d2dFactoryType*  
 Потоковая модель фабрики D2D и ресурсы, которые он создает.  
  
 *writeFactoryType*  
 Значение, указывающее, будет ли объект фабрики записи совместно или изолированной  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если фабрик были intilalizrd, FALSE — в противном случае  
  
## <a name="is32biticons"></a> AFX_GLOBAL_DATA::Is32BitIcons
Указывает, поддерживаются ли стандартные 32-разрядные значки.  
  
  
```  
BOOL Is32BitIcons() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если поддерживаются стандартные 32-разрядные значки; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает значение TRUE, если платформа поддерживает 32-разрядные значки встроенные и операционная система поддерживает 16 бит на пиксель, или более, если образы не отображаются в высокой контрастности.  
  
## <a name="isaccessibilitysupport"></a> AFX_GLOBAL_DATA::IsAccessibilitySupport
Указывает, включена ли поддержка Microsoft Active Accessibility.  
  
  
```  
BOOL IsAccessibilitySupport() const; 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если включена поддержка специальных возможностей; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Microsoft Active Accessibility был предыдущее решение по обеспечению доступности приложений. Microsoft UI Automation — это новая модель специальных возможностей для Microsoft Windows и предназначен для удовлетворения потребностей продуктов поддержки специальных возможностей и средств автоматизированного тестирования.   
  
 Используйте [AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport) метод, чтобы включить или отключить поддержку Active Accessibility.  
  

### <a name="see-also"></a>См. также  
 [Модель автоматизации пользовательского интерфейса и Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)

## <a name="isd2dinitialized"></a> AFX_GLOBAL_DATA::IsD2DInitialized
 Определяет, был ли инициализирован D2D  
  
  
```  
BOOL IsD2DInitialized() const; 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если D2D был инициализирован; в противном случае — значение FALSE.  
  
## <a name="isdwmcompositionenabled"></a> AFX_GLOBAL_DATA::IsDwmCompositionEnabled
Предоставляет простой способ для вызова метода [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) Windows.  
  
  
```  
BOOL IsDwmCompositionEnabled();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если [диспетчер окон рабочего стола](http://msdn.microsoft.com/library/windows/desktop/aa969540) составное включена; в противном случае — значение FALSE.  
  
### <a name="see-also"></a>См. также    
 [Диспетчер окон рабочего стола](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [Включение и контроль композиции DWM](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="ishighcontrastmode"></a> AFX_GLOBAL_DATA::IsHighContrastMode
 Указывает, отображаются ли сейчас изображения с высокой контрастностью.    
```  
BOOL IsHighContrastMode() const; 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если изображения отображаются в данный момент в режиме высокой контрастности черным и белым. в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 В режиме высокой контрастности, черный границ, окружающих света — белый и черный фон. В режиме высокой контрастности, белый границ, окружающих света являются черной и фон будет белым.  
  
## <a name="iswindowslayersupportavailable"></a> AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable
Указывает, поддерживает ли операционная система многослойные окна.  
  
  
```  
BOOL IsWindowsLayerSupportAvailable() const; 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если поддерживается многослойные окна; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Если поддерживаются многослойные окна, *смарт-закрепления* маркеры использовать многослойные окна.  
  
## <a name="m_busebuiltin32biticons"></a> AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons
Указывает, использует ли платформа стандартные 32-разрядные цветные значки или значки более низкого разрешения.  
  
  
```  
BOOL  m_bUseBuiltIn32BitIcons;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение TRUE указывает, что платформа использовать 32-разрядные цветные значки; Значение FALSE указывает, значки ниже разрешения. `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Конструктор инициализирует этот член значение true.  
  
 Этот элемент должен быть задан при запуске приложения.  
  
## <a name="m_busesystemfont"></a> AFX_GLOBAL_DATA::m_bUseSystemFont
Указывает, используется ли системный шрифт для меню, панелей инструментов и лент.  
  
  
```  
BOOL m_bUseSystemFont;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение TRUE указывает, использовать системный шрифт; в противном случае — значение FALSE. `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Конструктор инициализирует этот элемент, значение false.  
  
 Тестирование этот член не является единственным способом для платформы определить шрифта для использования. `AFX_GLOBAL_DATA::UpdateFonts` Метод также проверяет по умолчанию и альтернативное шрифты, чтобы определить, какие стили оформления будут доступны для применения к меню, панелей инструментов и лент.  
  
## <a name="m_hcurhand"></a> AFX_GLOBAL_DATA::m_hcurHand
Сохраняет дескриптор курсора в виде ладони.  
  
  
```  
HCURSOR m_hcurHand;  
```  
  
## <a name="m_hcurstretch"></a> AFX_GLOBAL_DATA::m_hcurStretch
Сохраняет дескриптор для курсора растяжения по горизонтали.  
  
  
```  
HCURSOR m_hcurStretch;  
```  

## <a name="m_hcurstretchvert"></a> AFX_GLOBAL_DATA::m_hcurStretchVert
Сохраняет дескриптор для курсора растяжения по вертикали.  
  
  
```  
HCURSOR m_hcurStretchVert;  
```  
  
## <a name="m_hicontool"></a> AFX_GLOBAL_DATA::m_hiconTool
Сохраняет дескриптор для значка средства.  
  
  
```  
HICON m_hiconTool;  
```  
## <a name="m_nautohidetoolbarmargin"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin
Указывает смещение от левой автоматически скрываемой панели инструментов до левой части панели закрепления.  
  
  
```  
int  m_nAutoHideToolBarMargin;  
```  
  
### <a name="remarks"></a>Примечания  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Конструктор инициализирует этот член до 4 пикселей.  
  
## <a name="m_nautohidetoolbarspacing"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing
Указывает интервал между автоматически скрываемыми панелями инструментов.  
  
  
```  
int   m_nAutoHideToolBarSpacing;  
```  
  
### <a name="remarks"></a>Примечания  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Конструктор инициализирует этот член до 14 пикселей.  
  
## <a name="m_ndragframethicknessdock"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessDock

Указывает толщину кадра перетаскивания, который используется для указания в закрепленном состоянии.  
  
  
```  
int  m_nDragFrameThicknessDock;  
```  
  
### <a name="remarks"></a>Примечания  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Конструктор инициализирует этот член для 3 пикселя.  
  
## <a name="m_ndragframethicknessfloat"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat
Указывает толщину кадра перетаскивания, который используется для указания состояния с плавающей запятой.  
  
  
```  
int  m_nDragFrameThicknessFloat;  
```  
  
### <a name="remarks"></a>Примечания  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Конструктор инициализирует этот член до 4 пикселей.  
  
## <a name="onsettingchange"></a> AFX_GLOBAL_DATA::OnSettingChange
Определяет текущее состояние для анимации меню рабочего стола и функций автоматического скрытия панели задач.  
  
  
```  
void OnSettingChange();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод задает framework переменные в состояние определенных атрибутов рабочий стол пользователя. Этот метод определяет текущее состояние анимация меню, исчезания меню и панели функций автоматического скрытия задач.  
  
## <a name="registerwindowclass"></a> AFX_GLOBAL_DATA::RegisterWindowClass
Регистрирует указанный класс окна MFC.  
  
  
```  
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```  
  
### <a name="parameters"></a>Параметры   
 [in] *lpszClassNamePrefix*  
 Имя класса окна для регистрации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полное имя зарегистрированного класса, если этот метод выполнен успешно; в противном случае [исключение ресурсов](http://msdn.microsoft.com/library/ddd99292-819b-4fa4-8371-b1954ed5856d).  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение — это список разделенных запятой *lpszClassNamePrefix* строки параметра, а также шестнадцатеричное текстовое представления дескрипторов текущего экземпляра приложения; курсор приложения, который представляет стрелку курсор, идентификатор которого равен IDC_ARROW; и кисть фона. Дополнительные сведения о регистрации классов окна MFC см. в разделе [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass).  
  
### <a name="see-also"></a>См. также    
 [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)   
 [AfxThrowResourceException](../../mfc/reference/exception-processing.md#afxthrowresourceexception)

## <a name="resume"></a> AFX_GLOBAL_DATA::Resume
 Повторно инициализирует Внутренние указатели функции, которые обращаются к методам, которые поддерживают Windows темы и стили оформления. 
  
  
```  
BOOL Resume();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE. В режиме отладки этот метод утверждает, если этот метод завершается неудачно.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, когда платформа получает [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) сообщения.  
  
## <a name="setlayeredattrib"></a> AFX_GLOBAL_DATA::SetLayeredAttrib
Предоставляет простой способ для вызова метода [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) Windows.  
  
  
```  
BOOL SetLayeredAttrib(
    HWND hwnd,  
    COLORREF crKey,  
    BYTE bAlpha,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Параметры   
 [in] *hwnd*  
 Дескриптор многослойные окна.  
  
 [in] *crKey*  
 Ключ цвета прозрачности, [диспетчер окон рабочего стола](http://msdn.microsoft.com/library/windows/desktop/aa969540) использует для создания слоистого окна.  
  
 [in] *bAlpha*  
 Альфа-значение, которое используется для описания непрозрачности слоистых окон.  
  
 [in] *dwFlags*  
 Побитовое сочетание (OR) флагов, которые определяют, какие параметры метода для использования. Укажите LWA_COLORKEY использовать *crKey* параметр тот цвет прозрачности. Укажите LWA_ALPHA использовать *bAlpha* параметр, чтобы определить прозрачность слоистых окон.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.   
 
### <a name="see-also"></a>См. также   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540)

## <a name="setmenufont"></a> AFX_GLOBAL_DATA::SetMenuFont
Создает указанный логический шрифт.  
  
  
```  
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры   
 [in] *lpLogFont*  
 Указатель на структуру, содержащую атрибуты шрифта.  
  
 [in] *bHorz*  
 Значение TRUE, чтобы указать, что текст выполняется по горизонтали; Значение FALSE, чтобы указать, что текст вертикально.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE. В режиме отладки этот метод утверждает, если этот метод завершается неудачно.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает горизонтальной шрифта regular подчеркнутый шрифт, а полужирный шрифт, используемый по умолчанию пунктов меню. При необходимости этот метод создает регулярное вертикального шрифта. Дополнительные сведения о логических шрифты, см. в разделе [CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#createfontindirect).  
  
## <a name="updatefonts"></a> AFX_GLOBAL_DATA::UpdateFonts
Повторно инициализирует логические шрифты, используемые платформой.  
  
  
```  
void UpdateFonts();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о логических шрифты, см. в разделе `CFont::CreateFontIndirect`.  
  
## <a name="updatesyscolors"></a> AFX_GLOBAL_DATA::UpdateSysColors
Инициализирует цвета, глубину цвета, кисти, перья и изображения, используемые платформой.  
  
  
```  
void UpdateSysColors();
```  
  
## <a name="biswindows7"></a> AFX_GLOBAL_DATA::bIsWindows7
Указывает, выполняется ли приложение под управлением Windows 7 или более поздней версии.  
  
  
```  
BOOL bIsWindows7;  
```  
  
## <a name="clractivecaptiongradient"></a> AFX_GLOBAL_DATA::clrActiveCaptionGradient
Задает цвет градиента заголовка активного окна. Обычно используется для закрепляемых панелей.  
  
  
```  
COLORREF clrActiveCaptionGradient;  
```  
  
## <a name="clrinactivecaptiongradient"></a> AFX_GLOBAL_DATA::clrInactiveCaptionGradient
Задает цвет градиента заголовка неактивного окна. Обычно используется для закрепляемых панелей.  
  
  
```  
COLORREF clrInactiveCaptionGradient;  
```  
  
## <a name="getitaskbarlist"></a> AFX_GLOBAL_DATA::GetITaskbarList
Создает и сохраняет в глобальных данных указатель на `ITaskBarList` интерфейс.  
  
  
```  
ITaskbarList *GetITaskbarList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `ITaskbarList` интерфейс успешное завершение создания панель объект списка задач; Значение NULL, если происходит сбой при создании или текущая операционная система меньше, чем Windows 7.  
  
## <a name="getitaskbarlist3"></a> AFX_GLOBAL_DATA::GetITaskbarList3
Создает и сохраняет в глобальных данных указатель на `ITaskBarList3` интерфейс.  
  
  
```  
ITaskbarList3 *GetITaskbarList3();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `ITaskbarList3` интерфейс успешное завершение создания панель объект списка задач; Значение NULL, если происходит сбой при создании или текущая операционная система меньше, чем Windows 7.  
  
## <a name="getshellautohidebars"></a> AFX_GLOBAL_DATA::GetShellAutohideBars
Определяет положения автоматически скрываемых панелей оболочки.  
  
  
```  
int GetShellAutohideBars();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целочисленное значение, закодированное флаги, определяющие расположение автоматическое скрытие полос. Комбинирует следующие значения: AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT, AFX_AUTOHIDE_RIGHT.  
  
## <a name="releasetaskbarrefs"></a> AFX_GLOBAL_DATA::ReleaseTaskBarRefs
Освобождает интерфейсы, полученные через `GetITaskbarList` и `GetITaskbarList3` методы.  
  
  
```  
void ReleaseTaskBarRefs();
```  
  
## <a name="shellcreateitemfromparsingname"></a> AFX_GLOBAL_DATA::ShellCreateItemFromParsingName
Создает и инициализирует объект элемента оболочки из имени синтаксического анализа.  
  
  
```  
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,  
    IBindCtx *pbc,  
    REFIID riid,  
    void **ppv);
```  
  
### <a name="parameters"></a>Параметры   
 *pszPath*  
 [in] Указатель на отображаемое имя.  
  
 *pbc*  
 Указатель на контекст привязки, который управляет операцию синтаксического анализа.  
  
 *riid*  
 Ссылку на идентификатор интерфейса.  
  
 *ppv*  
 [out] Когда эта функция возвращает, содержит указатель интерфейса, запрашиваемый в *riid*. Обычно это будет `IShellItem` или `IShellItem2`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если выполнение прошло успешно; в противном случае значение ошибки.  

