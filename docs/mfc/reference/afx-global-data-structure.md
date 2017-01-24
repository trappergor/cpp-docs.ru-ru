---
title: "Структура AFX_GLOBAL_DATA | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GLOBAL_DATA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX_GLOBAL_DATA - структура"
  - "AFX_GLOBAL_DATA - конструктор"
ms.assetid: c7abf2fb-ad5e-4336-a01d-260c29ed53a2
caps.latest.revision: 30
caps.handback.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура AFX_GLOBAL_DATA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `AFX_GLOBAL_DATA` содержит поля и методы, используемые для управления платформой или настройки внешнего вида и поведения приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct AFX_GLOBAL_DATA  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`|Создает структуру `AFX_GLOBAL_DATA` .|  
|`AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::Cleanup](#afx_global_data__cleanup)|Освобождает ресурсы, выделенные платформой, например кисти, шрифты и библиотеки DLL.|  
|[AFX_GLOBAL_DATA::D2D1MakeRotateMatrix](#afx_global_data__d2d1makerotatematrix)|Создает преобразование вращения, осуществляющее поворот на указанный угол вокруг указанной точки.|  
|[AFX_GLOBAL_DATA::DrawParentBackground](#afx_global_data__drawparentbackground)|Рисует фон родительского объекта элемента управления в заданной области.|  
|[AFX_GLOBAL_DATA::DrawTextOnGlass](#afx_global_data__drawtextonglass)|Рисует заданный текст в визуальном стиле указанной темы.|  
|[AFX_GLOBAL_DATA::ExcludeTag](#afx_global_data__excludetag)|Удаляет заданную пару тегов XML из указанного буфера.|  
|[AFX_GLOBAL_DATA::GetColor](#afx_global_data__getcolor)|Получает текущий цвет из указанного элемента пользовательского интерфейса.|  
|[AFX_GLOBAL_DATA::GetDirect2dFactory](#afx_global_data__getdirect2dfactory)|Получает указатель на интерфейс `ID2D1Factory` , хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.|  
|[AFX_GLOBAL_DATA::GetHandCursor](#afx_global_data__gethandcursor)|Извлекает стандартный курсор в виде руки, идентификатор которого равен `IDC_HAND`.|  
|[AFX_GLOBAL_DATA::GetITaskbarList](#afx_global_data__getitaskbarlist)|Создает и сохраняет в глобальных данных указатель на интерфейс ITaskBarList.|  
|[AFX_GLOBAL_DATA::GetITaskbarList3](#afx_global_data__getitaskbarlist3)|Создает и сохраняет в глобальных данных указатель на интерфейс ITaskBarList3.|  
|[AFX_GLOBAL_DATA::GetNonClientMetrics](#afx_global_data__getnonclientmetrics)|Получает метрики, связанные с неклиентской областью несвернутого окна.|  
|[AFX_GLOBAL_DATA::GetShellAutohideBars](#afx_global_data__getshellautohidebars)|Определяет положения автоматически скрываемых панелей оболочки.|  
|[AFX_GLOBAL_DATA::GetTextHeight](#afx_global_data__gettextheight)|Получает высоту символов текста в текущем шрифте.|  
|[AFX_GLOBAL_DATA::GetWICFactory](#afx_global_data__getwicfactory)|Получает указатель на интерфейс `IWICImagingFactory` , хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.|  
|[AFX_GLOBAL_DATA::GetWriteFactory](#afx_global_data__getwritefactory)|Получает указатель на интерфейс `IDWriteFactory` , хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#afx_global_data__isd2dinitialized)|Инициализирует фабрики `D2D`, `DirectWrite`и `WIC` . Данный метод следует вызывать до инициализации основного окна.|  
|[AFX_GLOBAL_DATA::Is32BitIcons](#afx_global_data__is32biticons)|Указывает, поддерживаются ли стандартные 32-разрядные значки.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#afx_global_data__isd2dinitialized)|Определяет, был ли инициализирован `D2D` .|  
|[AFX_GLOBAL_DATA::IsDwmCompositionEnabled](#afx_global_data__isdwmcompositionenabled)|Предоставляет простой способ для вызова метода [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) Windows.|  
|[AFX_GLOBAL_DATA::IsHighContrastMode](#afx_global_data__ishighcontrastmode)|Указывает, отображаются ли сейчас изображения с высокой контрастностью.|  
|[AFX_GLOBAL_DATA::OnSettingChange](#afx_global_data__onsettingchange)|Определяет текущее состояние для анимации меню рабочего стола и функций автоматического скрытия панели задач.|  
|[AFX_GLOBAL_DATA::RegisterWindowClass](#afx_global_data__registerwindowclass)|Регистрирует указанный класс окна MFC.|  
|[AFX_GLOBAL_DATA::ReleaseTaskBarRefs](#afx_global_data__releasetaskbarrefs)|Освобождает интерфейсы, полученные через методы GetITaskbarList и GetITaskbarList3.|  
|[AFX_GLOBAL_DATA::Resume](#afx_global_data__resume)|Повторно инициализирует внутренние указатели функции, которые обращаются к методам, поддерживающим [темы и стили оформления](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx)Windows.|  
|[AFX_GLOBAL_DATA::SetLayeredAttrib](#afx_global_data__setlayeredattrib)|Предоставляет простой способ для вызова метода [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) Windows.|  
|[AFX_GLOBAL_DATA::SetMenuFont](#afx_global_data__setmenufont)|Создает указанный логический шрифт.|  
|[AFX_GLOBAL_DATA::ShellCreateItemFromParsingName](#afx_global_data__shellcreateitemfromparsingname)|Создает и инициализирует объект элемента оболочки из имени синтаксического анализа.|  
|[AFX_GLOBAL_DATA::UpdateFonts](#afx_global_data__updatefonts)|Повторно инициализирует логические шрифты, используемые платформой.|  
|[AFX_GLOBAL_DATA::UpdateSysColors](#afx_global_data__updatesyscolors)|Инициализирует цвета, глубину цвета, кисти, перья и изображения, используемые платформой.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#afx_global_data__enableaccessibilitysupport)|Включает или отключает поддержку Microsoft Active Accessibility. Active Accessibility предлагает надежные методы для предоставления информации об элементах пользовательского интерфейса.|  
|[AFX_GLOBAL_DATA::IsAccessibilitySupport](#afx_global_data__isaccessibilitysupport)|Указывает, включена ли поддержка Microsoft Active Accessibility.|  
|[AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable](#afx_global_data__iswindowslayersupportavailable)|Указывает, поддерживает ли операционная система многослойные окна.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport](#afx_global_data__bisosalphablendingsupport)|Указывает, поддерживает ли текущая операционная система альфа-смешение.|  
|[AFX_GLOBAL_DATA::bIsWindows7](#afx_global_data__biswindows7)|Указывает, выполняется ли приложение в ОС Windows 7 или более поздней версии.|  
|[AFX_GLOBAL_DATA::clrActiveCaptionGradient](#afx_global_data__clractivecaptiongradient)|Задает цвет градиента для активного заголовка. Обычно используется для закрепляемых панелей.|  
|[AFX_GLOBAL_DATA::clrInactiveCaptionGradient](#afx_global_data__clrinactivecaptiongradient)|Задает цвет градиента для неактивного заголовка. Обычно используется для закрепляемых панелей.|  
|[AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons](#afx_global_data__m_busebuiltin32biticons)|Указывает, использует ли платформа стандартные 32-разрядные цветные значки или значки более низкого разрешения.|  
|[AFX_GLOBAL_DATA::m_bUseSystemFont](#afx_global_data__m_busesystemfont)|Указывает, используется ли системный шрифт для меню, панелей инструментов и лент.|  
|[AFX_GLOBAL_DATA::m_hcurHand](#afx_global_data__m_hcurhand)|Сохраняет дескриптор курсора в виде ладони.|  
|[AFX_GLOBAL_DATA::m_hcurStretch](#afx_global_data__m_hcurstretch)|Сохраняет дескриптор для курсора растяжения по горизонтали.|  
|[AFX_GLOBAL_DATA::m_hcurStretchVert](#afx_global_data__m_hcurstretchvert)|Сохраняет дескриптор для курсора растяжения по вертикали.|  
|[AFX_GLOBAL_DATA::m_hiconTool](#afx_global_data__m_hicontool)|Сохраняет дескриптор для значка средства.|  
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin](#afx_global_data__m_nautohidetoolbarmargin)|Указывает смещение от самой левой автоматически скрываемой панели инструментов до левой части панели стыковки.|  
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing](#afx_global_data__m_nautohidetoolbarspacing)|Указывает интервал между автоматически скрываемыми панелями инструментов.|  
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](#afx_global_data__m_ndragframethicknessdock)|Указывает толщину кадра перетаскивания, который используется для взаимодействия в закрепленном состоянии.|  
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](#afx_global_data__m_ndragframethicknessfloat)|Указывает толщину кадра перетаскивания, который используется для взаимодействия в плавающем состоянии.|  
  
## <a name="remarks"></a>Примечания  
 Большинство данных в структуре `AFX_GLOBAL_DATA` инициализируется при запуске приложения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxglobals.h  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


## <a name="a-nameafxglobaldatabisosalphablendingsupporta-afxglobaldatabisosalphablendingsupport"></a><a name="afx_global_data__bisosalphablendingsupport"></a> AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport
Указывает, поддерживает ли операционная система альфа-смешения.  
  
  
```  
BOOL  bIsOSAlphaBlendingSupport;  
```  
  
## <a name="remarks"></a>Примечания  
 `TRUE` Указывает, что поддерживается альфа-смешение; в противном случае — `FALSE`.  
  

## <a name="a-nameafxglobaldatacleanupa-afxglobaldatacleanup"></a><a name="afx_global_data__cleanup"></a> AFX_GLOBAL_DATA::Cleanup
Освобождает ресурсы, выделенные платформой, например кисти, шрифты и библиотеки DLL.  
  
  
```  
void CleanUp();
```  
## <a name="a-nameafxglobaldatad2d1makerotatematrixa-afxglobaldatad2d1makerotatematrix"></a><a name="afx_global_data__d2d1makerotatematrix"></a> AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
Создает преобразование вращения, осуществляющее поворот на указанный угол вокруг указанной точки.  
  
  
```  
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,  
    D2D1_POINT_2F center,  
    D2D1_MATRIX_3X2_F *matrix);
```  
  
#### <a name="parameters"></a>Параметры  
 `angle`  
 Угол поворота по часовой стрелке в градусах.  
  
 `center`  
 Точки, вокруг которой выполняется поворот.  
  
 `matrix`  
 При возвращении данного метода содержит новый преобразование поворота. Для этого параметра необходимо выделить хранилище.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В противном случае возвращает значение S_OK в случае успешного выполнения или значение ошибки.  
  
## <a name="a-nameafxglobaldatadrawparentbackgrounda-afxglobaldatadrawparentbackground"></a><a name="afx_global_data__drawparentbackground"></a> AFX_GLOBAL_DATA::DrawParentBackground
Рисует фон родительского объекта элемента управления в заданной области.  
  
  
```  
BOOL DrawParentBackground(
    CWnd* pWnd,   
    CDC* pDC,   
    LPRECT lpRect = NULL);
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Указатель окна элемента управления.  
  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `lpRect`  
 Указатель на прямоугольник, ограничивающий область для рисования. Значение по умолчанию — `NULL`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если этот метод выполнен успешно; в противном случае — `FALSE`.  
  
## <a name="a-nameafxglobaldatadrawtextonglassa-afxglobaldatadrawtextonglass"></a><a name="afx_global_data__drawtextonglass"></a> AFX_GLOBAL_DATA::DrawTextOnGlass
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
  
#### <a name="parameters"></a>Параметры  
 [in] `hTheme`  
 Дескриптор данных темы окна или `NULL`. Платформа использует указанную тему для рисования текста, если этот параметр отличен от `NULL` и поддерживаются темы. В противном случае платформа не использует тему для рисования текста.  
  
 Используйте метод [OpenThemeData](http://msdn.microsoft.com/library/windows/desktop/bb759821) для создания `HTHEME`.  
  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `iPartId`  
 Часть элемента управления, имеющая нужный вид текста. Дополнительные сведения см. в столбце "Части" в таблице [Части и состояния](http://msdn.microsoft.com/library/windows/desktop/bb773210). Если это значение равно 0, текст рисуется с помощью шрифта по умолчанию или шрифта, выбранного в контексте устройства.  
  
 [in] `iStateId`  
 Состояние элемента управления, имеющее нужный вид текста. Дополнительные сведения см. в столбце "Состояния" в таблице [Части и состояния](http://msdn.microsoft.com/library/windows/desktop/bb773210).  
  
 [in] `strText`  
 Текст для отрисовки.  
  
 [in] `rect`  
 Границы области, в которой рисуется заданный текст.  
  
 [in] `dwFlags`  
 Побитовое сочетание (OR) флагов, определяющих способ рисования указанного текста.  
  
 Если `hTheme` параметр `NULL` или если темы не поддерживается и не включен, `nFormat` параметр [CDC::DrawText](../Topic/CDC%20Class.md#cdc__drawtext) Метод описывает допустимые флаги. Если темы поддерживаются, допустимые флаги описываются параметром `dwFlags` метода [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) .  
  
 [in] `nGlowSize`  
 Размер эффекта свечения, рисуемого на фоне перед рисованием заданного текста. Значение по умолчанию — 0.  
  
 [in] `clrText`  
 Цвет рисования заданного текста. Значением по умолчанию является цвет по умолчанию.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если тема используется для рисования указанный текст; в противном случае — `FALSE`.  
  
## <a name="remarks"></a>Примечания  
 Тема определяет визуальный стиль приложения. Тема не используется для рисования текста, если параметру `hTheme` задано значение `NULL`, или если метод [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) не поддерживается, или если отключена композиция [диспетчера окон рабочего стола](http://msdn.microsoft.com/library/windows/desktop/aa969540) (DWM).  
  
 
## <a name="see-also"></a>См. также  
 [Структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [Частей и состояний](http://msdn.microsoft.com/library/windows/desktop/bb773210)   
 [CDC::DrawText](../Topic/CDC%20Class.md#cdc__drawtext)   
 [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317)   
 [Диспетчер окон рабочего стола](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [Включение и управления компоновки DWM](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="a-nameafxglobaldataenableaccessibilitysupporta-afxglobaldataenableaccessibilitysupport"></a><a name="afx_global_data__enableaccessibilitysupport"></a> AFX_GLOBAL_DATA::EnableAccessibilitySupport
Включает или отключает поддержку Microsoft Active Accessibility.  
  
  
```  
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE` Чтобы включить поддержку специальных возможностей; `FALSE` Отключение поддержки специальных возможностей. Значение по умолчанию — `TRUE`.  
  
## <a name="remarks"></a>Примечания  
 Active Accessibility является технология на основе COM, которая улучшает программами и работы операционной системы Windows вместе с продукты поддержки специальных возможностей. Он предоставляет надежные методы для вывода информации об элементах пользовательского интерфейса. Однако доступна новая модель специальных возможностей, называется Microsoft UI Automation. Сравнение этих двух технологий см. в разделе [модели автоматизации пользовательского Интерфейса и Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md).  
  
 Используйте [AFX_GLOBAL_DATA::IsAccessibilitySupport](#afx_global_data__IsAccessibilitySupport.md) метод, чтобы определить, включена ли поддержка Microsoft Active Accessibility.  
  
 
## <a name="see-also"></a>См. также  
 [Автоматизация пользовательского Интерфейса и Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md)   
 [AFX_GLOBAL_DATA::IsAccessibilitySupport](#afx_global_data__IsAccessibilitySupport.md)

## <a name="a-nameafxglobaldataexcludetaga-afxglobaldataexcludetag"></a><a name="afx_global_data__excludetag"></a> AFX_GLOBAL_DATA::ExcludeTag
Удаляет заданную пару тегов XML из указанного буфера.  
  
  
```  
BOOL ExcludeTag(
    CString& strBuffer,  
    LPCTSTR lpszTag,  
    CString& strTag,  
    BOOL bIsCharsList = FALSE);
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `strBuffer`  
 Буфер текста.  
  
 [in] `lpszTag`  
 Имя пары открывающих и закрывающих тегов XML.  
  
 [выходной] `strTag`  
 По возвращении из этого метода `strTag` параметр содержит текст, который находится между открывающим и закрывающим XML теги, которые именуются по `lpszTag` параметр. Все начальные и конечные пробелы удаляются из результат.  
  
 [in] `bIsCharsList`  
 `TRUE` для преобразования символов для escape-символов в `strTag` параметр в фактические escape-знаки `FALSE` не для выполнения преобразования. Значение по умолчанию — `FALSE`. Дополнительные сведения см. в разделе "Замечания".  
  
## <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если этот метод выполнен успешно; в противном случае — `FALSE`.  
  
## <a name="remarks"></a>Примечания  
 Пару тегов XML состоит из именованных открывающие и закрывающие теги, которые указывают на начало и конец выполнения текста в указанный буфер.  `strBuffer` Указывает буфер и `lpszTag` задает имя XML-теги.  
  
 Символы в следующей таблице можно используйте для кодирования набор escape-символов в указанный буфер. Укажите `TRUE` для `bIsCharsList` параметра для преобразования символов в `strTag` параметр в фактические escape-символы. В следующей таблице использует [_T()](../../c-runtime-library/data-type-mappings.md) макрос для указания символа и escape-символ строки.  
  
|Символ|Escape-символ|  
|------------|----------------------|  
|_T("\\\t")|_T("\t")|  
|_T("\\\n")|_T("\n")|  
|_T("\\\r")|_T("\r")|  
|_T("\\\b")|_T("\b")|  
|_T("LT")|_T("\<")|  
|_T("GT")|_T(">")|  
|_T("AMP")|_T("&")|  
  
## <a name="a-nameafxglobaldatagetcolora-afxglobaldatagetcolor"></a><a name="afx_global_data__getcolor"></a> AFX_GLOBAL_DATA::GetColor
Получает текущий цвет из указанного элемента пользовательского интерфейса.  
  
  
```  
COLORREF GetColor(int nColor);
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `nColor`  
 Значение, указывающее элемент пользовательского интерфейса, цвет которого извлекается. Список допустимых значений см. в разделе `nIndex` параметр [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) метод.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение цвета RGB указанный элемент пользовательского интерфейса. Дополнительные сведения см. в разделе "Замечания".  
  
## <a name="remarks"></a>Примечания  
 Если `nColor` параметр выходит за пределы диапазона, возвращаемое значение равно нулю. Поскольку ноль является допустимое значение RGB, нельзя использовать этот метод для определения, поддерживается ли системный цвет с использованием текущей операционной системы. Вместо этого используйте [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927) метод, возвращающий `NULL` Если цвет не поддерживается.  
  
## <a name="see-also"></a>См. также  

 [Функция GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927)

## <a name="a-nameafxglobaldatagetdirect2dfactorya-afxglobaldatagetdirect2dfactory"></a><a name="afx_global_data__getdirect2dfactory"></a> AFX_GLOBAL_DATA::GetDirect2dFactory
 Возвращает указатель на интерфейс ID2D1Factory, хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.  
  
  
```  
ID2D1Factory* GetDirect2dFactory();
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Factory, если создания фабрики успешно, или значение NULL, если происходит сбой создания или текущая операционная система отсутствует поддержка D2D.  
  
AFX_GLOBAL_DATA::GetHandCursor извлекает стандартные курсора, в виде руки и идентификатор которого равен `IDC_HAND`.  
  
  
```  
HCURSOR GetHandCursor();
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Дескриптор курсор в виде руки.  

## <a name="a-nameafxglobaldatagetnonclientmetricsa-afxglobaldatagetnonclientmetrics"></a><a name="afx_global_data__getnonclientmetrics"></a> AFX_GLOBAL_DATA::GetNonClientMetrics
Получает метрики, связанные с неклиентской областью несвернутого окна.  
  
  
```  
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```  
  
#### <a name="parameters"></a>Параметры  
 [in, out] `info`  
 Объект [NONCLIENTMETRICS](http://msdn.microsoft.com/library/windows/desktop/ff729175) структуру, содержащую масштабируемой показатели, связанные с неклиентской области несвернутого окна.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если этот метод выполнен успешно; в противном случае — `FALSE`.  
 
  
## <a name="see-also"></a>См. также   
 [Структура NONCLIENTMETRICS](http://msdn.microsoft.com/library/windows/desktop/ff729175)

## <a name="a-nameafxglobaldatagettextheighta-afxglobaldatagettextheight"></a><a name="afx_global_data__gettextheight"></a> AFX_GLOBAL_DATA::GetTextHeight
 Получает высоту символов текста в текущем шрифте.  
  
  
```  
int GetTextHeight(BOOL bHorz = TRUE);
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `bHorz`  
 `TRUE` Для получения высота символов, если отрезки текста по горизонтали; `FALSE` для получения высота символов, если текст располагается вертикально. Значение по умолчанию — `TRUE`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Высота текущего шрифта, отсчитывается от его выносным элементом для его подстрочный элемент символа.  
  
## <a name="a-nameafxglobaldatagetwicfactorya-afxglobaldatagetwicfactory"></a><a name="afx_global_data__getwicfactory"></a> AFX_GLOBAL_DATA::GetWICFactory
Возвращает указатель на интерфейс IWICImagingFactory, хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.  
  
  
```  
IWICImagingFactory* GetWICFactory();
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IWICImagingFactory, если для создания фабрики успешно, или значение NULL, если происходит сбой при создании или текущая операционная система не поддерживают WIC.  
  
## <a name="a-nameafxglobaldatagetwritefactorya-afxglobaldatagetwritefactory"></a><a name="afx_global_data__getwritefactory"></a> AFX_GLOBAL_DATA::GetWriteFactory
Возвращает указатель на интерфейс IDWriteFactory, хранящийся в глобальных данных. Если интерфейс не инициализирован, он создается с параметрами по умолчанию.  
  
  
```  
IDWriteFactory* GetWriteFactory();
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IDWriteFactory, если создания фабрики успешно, или значение NULL, если происходит сбой создания или текущая операционная система не поддерживают DirectWrite.  
 
## <a name="a-nameafxglobaldatainitd2da-afxglobaldatainitd2d"></a><a name="afx_global_data__initd2d"></a> AFX_GLOBAL_DATA::InitD2D
Инициализирует фабрики D2D, DirectWrite и WIC. Данный метод следует вызывать до инициализации основного окна.  
  
  
```  
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
#### <a name="parameters"></a>Параметры  
 `d2dFactoryType`  
 Потоковая модель фабрики D2D и ресурсы, которые он создает.  
  
 `writeFactoryType`  
 Значение, указывающее, будет ли объект фабрики записи совместно или изолированной  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если фабрик были intilalizrd, FALSE — в противном случае  
  
## <a name="a-nameafxglobaldatais32biticonsa-afxglobaldatais32biticons"></a><a name="afx_global_data__is32biticons"></a> AFX_GLOBAL_DATA::Is32BitIcons
Указывает, поддерживаются ли стандартные 32-разрядные значки.  
  
  
```  
BOOL Is32BitIcons() const;

 
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если предварительно 32-разрядных значков поддерживаются; в противном случае — `FALSE`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод возвращает `TRUE` Если платформа поддерживает встроенные значки 32-разрядной и если операционная система поддерживает 16 бит на пиксель или более и изображения не будут отображаться в высокой контрастности.  
  
## <a name="a-nameafxglobaldataisaccessibilitysupporta-afxglobaldataisaccessibilitysupport"></a><a name="afx_global_data__isaccessibilitysupport"></a> AFX_GLOBAL_DATA::IsAccessibilitySupport
Указывает, включена ли поддержка Microsoft Active Accessibility.  
  
  
```  
BOOL IsAccessibilitySupport() const;

 
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если включена поддержка специальных возможностей. в противном случае — `FALSE`.  
  
## <a name="remarks"></a>Примечания  
 Microsoft Active Accessibility — предыдущее решение по обеспечению доступности приложений. Microsoft UI Automation — это новая модель специальных возможностей для Microsoft Windows и предназначен для удовлетворения потребностей продукты поддержки специальных возможностей и автоматизированных средств тестирования. Дополнительные сведения см. в разделе [модели автоматизации пользовательского Интерфейса и Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md).  
  
 Используйте [AFX_GLOBAL_DATA::EnableAccessibilitySupport](#afx_global_data__EnableAccessibilitySupport.md) метод, чтобы включить или отключить поддержку Active Accessibility.  
  

## <a name="see-also"></a>См. также  
 [Автоматизация пользовательского Интерфейса и Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md)

## <a name="a-nameafxglobaldataisd2dinitializeda-afxglobaldataisd2dinitialized"></a><a name="afx_global_data__isd2dinitialized"></a> AFX_GLOBAL_DATA::IsD2DInitialized
 Определяет, был ли инициализирован D2D  
  
  
```  
BOOL IsD2DInitialized() const;

 
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если D2D был инициализирован; в противном случае — значение FALSE.  
  
## <a name="a-nameafxglobaldataisdwmcompositionenableda-afxglobaldataisdwmcompositionenabled"></a><a name="afx_global_data__isdwmcompositionenabled"></a> AFX_GLOBAL_DATA::IsDwmCompositionEnabled
Предоставляет простой способ для вызова метода [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) Windows.  
  
  
```  
BOOL IsDwmCompositionEnabled();
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если [Диспетчер окон рабочего стола](http://msdn.microsoft.com/library/windows/desktop/aa969540) составное включен; в противном случае — `FALSE`.  
  
## <a name="see-also"></a>См. также    
 [Диспетчер окон рабочего стола](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [Включение и управления компоновки DWM](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="a-nameafxglobaldataishighcontrastmodea-afxglobaldataishighcontrastmode"></a><a name="afx_global_data__ishighcontrastmode"></a> AFX_GLOBAL_DATA::IsHighContrastMode
 Указывает, отображаются ли сейчас изображения с высокой контрастностью.    
```  
BOOL IsHighContrastMode() const;

 
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если изображения, отображаются в черный или белый высокой контрастности; в противном случае — `FALSE`.  
  
## <a name="remarks"></a>Примечания  
 В черной высокой контрастности границ, окружающих свет белый и черный фон. В режиме высокой контрастности белый границ, окружающих свет черным и имеет белый фон.  
  
## <a name="a-nameafxglobaldataiswindowslayersupportavailablea-afxglobaldataiswindowslayersupportavailable"></a><a name="afx_global_data__iswindowslayersupportavailable"></a> AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable
Указывает, поддерживает ли операционная система многослойные окна.  
  
  
```  
BOOL IsWindowsLayerSupportAvailable() const;

 
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если поддерживается многослойные окна; в противном случае — `FALSE`.  
  
## <a name="remarks"></a>Примечания  
 Если поддерживается многослойные окна *смарт-закрепления* использовать маркеры многослойные окна.  
  
## <a name="a-nameafxglobaldatambusebuiltin32biticonsa-afxglobaldatambusebuiltin32biticons"></a><a name="afx_global_data__m_busebuiltin32biticons"></a> AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons
Указывает, использует ли платформа стандартные 32-разрядные цветные значки или значки более низкого разрешения.  
  
  
```  
BOOL  m_bUseBuiltIn32BitIcons;  
```  
  
## <a name="remarks"></a>Примечания  
 `TRUE` Указывает, что платформа использует 32-разрядных цветных значков; `FALSE` указывает низким разрешением значков.  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Конструктор инициализирует этот элемент для `TRUE`.  
  
 Этот элемент должен устанавливаться при запуске приложения.  
  
## <a name="a-nameafxglobaldatambusesystemfonta-afxglobaldatambusesystemfont"></a><a name="afx_global_data__m_busesystemfont"></a> AFX_GLOBAL_DATA::m_bUseSystemFont
Указывает, используется ли системный шрифт для меню, панелей инструментов и лент.  
  
  
```  
BOOL m_bUseSystemFont;  
```  
  
## <a name="remarks"></a>Примечания  
 `TRUE` Указывает, можно использовать системный шрифт; в противном случае — `FALSE`.  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Конструктор инициализирует этот элемент для `FALSE`.  
  
 Тестирование этот член не является единственным способом для платформы определить шрифт для использования.  `AFX_GLOBAL_DATA::UpdateFonts` Метод также проверяет шрифты по умолчанию и альтернативное, чтобы определить, какие визуальные стили доступны для применения к меню, панелей инструментов и ленты.  
  
## <a name="a-nameafxglobaldatamhcurhanda-afxglobaldatamhcurhand"></a><a name="afx_global_data__m_hcurhand"></a> AFX_GLOBAL_DATA::m_hcurHand
Сохраняет дескриптор курсора в виде ладони.  
  
  
```  
HCURSOR m_hcurHand;  
```  
  
## <a name="a-nameafxglobaldatamhcurstretcha-afxglobaldatamhcurstretch"></a><a name="afx_global_data__m_hcurstretch"></a> AFX_GLOBAL_DATA::m_hcurStretch
Сохраняет дескриптор для курсора растяжения по горизонтали.  
  
  
```  
HCURSOR m_hcurStretch;  
```  

## <a name="a-nameafxglobaldatamhcurstretchverta-afxglobaldatamhcurstretchvert"></a><a name="afx_global_data__m_hcurstretchvert"></a> AFX_GLOBAL_DATA::m_hcurStretchVert
Сохраняет дескриптор для курсора растяжения по вертикали.  
  
  
```  
HCURSOR m_hcurStretchVert;  
```  
  
## <a name="a-nameafxglobaldatamhicontoola-afxglobaldatamhicontool"></a><a name="afx_global_data__m_hicontool"></a> AFX_GLOBAL_DATA::m_hiconTool
Сохраняет дескриптор для значка средства.  
  
  
```  
HICON m_hiconTool;  
```  
## <a name="a-nameafxglobaldatamnautohidetoolbarmargina-afxglobaldatamnautohidetoolbarmargin"></a><a name="afx_global_data__m_nautohidetoolbarmargin"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin
Указывает смещение от левого Автоскрытие инструментов в левой части панели закрепления.  
  
  
```  
int   m_nAutoHideToolBarMargin;  
```  
  
## <a name="remarks"></a>Примечания  
  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Конструктор инициализирует этот элемент 4 пикселей.  
  
## <a name="a-nameafxglobaldatamnautohidetoolbarspacinga-afxglobaldatamnautohidetoolbarspacing"></a><a name="afx_global_data__m_nautohidetoolbarspacing"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing
Указывает интервал между автоматически скрываемыми панелями инструментов.  
  
  
```  
int   m_nAutoHideToolBarSpacing;  
```  
  
## <a name="remarks"></a>Примечания  
  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Конструктор инициализирует этот элемент 14 точек.  
  
## <a name="a-nameafxglobaldatamndragframethicknessdocka-afxglobaldatamndragframethicknessdock"></a><a name="afx_global_data__m_ndragframethicknessdock"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessDock

Определяет толщину рамки перетаскивания, используется для указания закрепленном состоянии.  
  
  
```  
int   m_nDragFrameThicknessDock;  
```  
  
## <a name="remarks"></a>Примечания  
  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Конструктор инициализирует этот элемент 3 пикселя.  
  
## <a name="a-nameafxglobaldatamndragframethicknessfloata-afxglobaldatamndragframethicknessfloat"></a><a name="afx_global_data__m_ndragframethicknessfloat"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat
Определяет толщину рамки перетаскивания, используется для указания состояния с плавающей запятой.  
  
  
```  
int   m_nDragFrameThicknessFloat;  
```  
  
## <a name="remarks"></a>Примечания  
  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` Конструктор инициализирует этот элемент 4 пикселей.  
  
## <a name="a-nameafxglobaldataonsettingchangea-afxglobaldataonsettingchange"></a><a name="afx_global_data__onsettingchange"></a> AFX_GLOBAL_DATA::OnSettingChange
Определяет текущее состояние для анимации меню рабочего стола и функций автоматического скрытия панели задач.  
  
  
```  
void OnSettingChange();
```  
  
## <a name="remarks"></a>Примечания  
 Этот метод устанавливает переменные framework состояние определенных атрибутов рабочий стол пользователя. Этот метод определяет текущее состояние анимация меню, исчезания меню и панели функции автоскрытия задач.  
  
## <a name="a-nameafxglobaldataregisterwindowclassa-afxglobaldataregisterwindowclass"></a><a name="afx_global_data__registerwindowclass"></a> AFX_GLOBAL_DATA::RegisterWindowClass
Регистрирует указанный класс окна MFC.  
  
  
```  
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `lpszClassNamePrefix`  
 Имя класса окна для регистрации.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Полное имя зарегистрированного класса, если этот метод выполнен успешно; в противном случае — [исключение ресурсов](../Topic/AfxThrowResourceException.md).  
  
## <a name="remarks"></a>Примечания  
 Возвращаемое значение является списком разделенных запятой `lpszClassNamePrefix` Строка параметра и представления шестнадцатеричное число дескрипторов текущего экземпляра приложения; курсора приложения, который представляет курсор в виде стрелки, идентификатор которого равен IDC_ARROW; и кисть фона. Дополнительные сведения о регистрации классов окна MFC см. в разделе [AfxRegisterClass](../Topic/Application%20Information%20and%20Management.md#afxregisterclass).  
  
## <a name="see-also"></a>См. также    
 [AfxRegisterClass](../Topic/Application%20Information%20and%20Management.md#afxregisterclass)   
 [AfxThrowResourceException](../../mfc/reference/exception-processing.md#afxthrowresourceexception)

## <a name="a-nameafxglobaldataresumea-afxglobaldataresume"></a><a name="afx_global_data__resume"></a> AFX_GLOBAL_DATA::Resume
 Повторно инициализирует указатели внутренней функции, доступ к методам, которые поддерживают Windows тем и стилей оформления. 
  
  
```  
BOOL Resume();
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если этот метод выполнен успешно; в противном случае — `FALSE`. В режиме отладки этот метод подтверждает, если этот метод завершается неудачно.  
  
## <a name="remarks"></a>Примечания  
 Этот метод вызывается, когда платформа получает [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) сообщение.  
  
## <a name="a-nameafxglobaldatasetlayeredattriba-afxglobaldatasetlayeredattrib"></a><a name="afx_global_data__setlayeredattrib"></a> AFX_GLOBAL_DATA::SetLayeredAttrib
Предоставляет простой способ для вызова метода [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) Windows.  
  
  
```  
BOOL SetLayeredAttrib(
    HWND hwnd,  
    COLORREF crKey,  
    BYTE bAlpha,  
    DWORD dwFlags);
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `hwnd`  
 Дескриптор многослойные окна.  
  
 [in] `crKey`  
 Цвет прозрачности ключ, который [Диспетчер окон рабочего стола](http://msdn.microsoft.com/library/windows/desktop/aa969540) используется для создания многоуровневых окон.  
  
 [in] `bAlpha`  
 Альфа-значение, которое используется для описания непрозрачности многослойные окна.  
  
 [in] `dwFlags`  
 Побитовое сочетание (или) флагов, определяющих параметры метода. Укажите LWA_COLORKEY для использования `crKey` параметр прозрачности. Укажите LWA_ALPHA для использования `bAlpha` параметр, чтобы определить степень непрозрачности многоуровневых окон.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если этот метод выполнен успешно; в противном случае — `FALSE`.   
 
## <a name="see-also"></a>См. также   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540)

## <a name="a-nameafxglobaldatasetmenufonta-afxglobaldatasetmenufont"></a><a name="afx_global_data__setmenufont"></a> AFX_GLOBAL_DATA::SetMenuFont
Создает указанный логический шрифт.  
  
  
```  
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz);
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `lpLogFont`  
 Указатель на структуру, содержащую атрибуты шрифта.  
  
 [in] `bHorz`  
 `TRUE` Чтобы указать, что текст выполняется по горизонтали; `FALSE` для указания, что текст располагается вертикально.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если этот метод выполнен успешно; в противном случае — `FALSE`. В режиме отладки этот метод подтверждает, если этот метод завершается неудачно.  
  
## <a name="remarks"></a>Примечания  
 Этот метод создает горизонтальной шрифт обычного подчеркнутого шрифта и полужирный шрифт, используемый по умолчанию элементы меню. Этот метод также создает регулярные вертикального шрифта. Дополнительные сведения о логических шрифты в разделе [CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#cfont__createfontindirect).  
  
## <a name="a-nameafxglobaldataupdatefontsa-afxglobaldataupdatefonts"></a><a name="afx_global_data__updatefonts"></a> AFX_GLOBAL_DATA::UpdateFonts
Повторно инициализирует логические шрифты, используемые платформой.  
  
  
```  
void UpdateFonts();
```  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о логических шрифты в разделе `CFont::CreateFontIndirect`.  
  
## <a name="a-nameafxglobaldataupdatesyscolorsa-afxglobaldataupdatesyscolors"></a><a name="afx_global_data__updatesyscolors"></a> AFX_GLOBAL_DATA::UpdateSysColors
Инициализирует цвета, глубину цвета, кисти, перья и изображения, используемые платформой.  
  
  
```  
void UpdateSysColors();
```  
  
## <a name="a-nameafxglobaldatabiswindows7a-afxglobaldatabiswindows7"></a><a name="afx_global_data__biswindows7"></a> AFX_GLOBAL_DATA::bIsWindows7
Указывает, выполняется ли приложение под управлением Windows 7 или более поздней версии.  
  
  
```  
BOOL bIsWindows7;  
```  
  
## <a name="a-nameafxglobaldataclractivecaptiongradienta-afxglobaldataclractivecaptiongradient"></a><a name="afx_global_data__clractivecaptiongradient"></a> AFX_GLOBAL_DATA::clrActiveCaptionGradient
Задает цвет градиента для активных заголовков. Обычно используется для закрепляемых панелей.  
  
  
```  
COLORREF clrActiveCaptionGradient;  
```  
  
## <a name="a-nameafxglobaldataclrinactivecaptiongradienta-afxglobaldataclrinactivecaptiongradient"></a><a name="afx_global_data__clrinactivecaptiongradient"></a> AFX_GLOBAL_DATA::clrInactiveCaptionGradient
Задает цвет градиента для неактивного заголовка. Обычно используется для закрепляемых панелей.  
  
  
```  
COLORREF clrInactiveCaptionGradient;  
```  
  
## <a name="a-nameafxglobaldatagetitaskbarlista-afxglobaldatagetitaskbarlist"></a><a name="afx_global_data__getitaskbarlist"></a> AFX_GLOBAL_DATA::GetITaskbarList
Создает и сохраняет указатель на глобальные данные `ITaskBarList` интерфейса.  
  
  
```  
ITaskbarList *GetITaskbarList();
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на `ITaskbarList` интерфейс, если после успешного создания задачи панели объекта списка; `NULL` ли сбой создания ли текущая операционная система меньше, чем Windows 7.  
  
## <a name="a-nameafxglobaldatagetitaskbarlist3a-afxglobaldatagetitaskbarlist3"></a><a name="afx_global_data__getitaskbarlist3"></a> AFX_GLOBAL_DATA::GetITaskbarList3
Создает и сохраняет указатель на глобальные данные `ITaskBarList3` интерфейса.  
  
  
```  
ITaskbarList3 *GetITaskbarList3();
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на `ITaskbarList3` интерфейс, если после успешного создания задачи панели объекта списка; `NULL` ли сбой создания ли текущая операционная система меньше, чем Windows 7.  
  
## <a name="a-nameafxglobaldatagetshellautohidebarsa-afxglobaldatagetshellautohidebars"></a><a name="afx_global_data__getshellautohidebars"></a> AFX_GLOBAL_DATA::GetShellAutohideBars
Определяет положения автоматически скрываемых панелей оболочки.  
  
  
```  
int GetShellAutohideBars();
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Целочисленное значение, закодированное флаги, определяющие позиции автоматическое скрытие полос. Она может объединять следующие значения: AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT, AFX_AUTOHIDE_RIGHT.  
  
## <a name="a-nameafxglobaldatareleasetaskbarrefsa-afxglobaldatareleasetaskbarrefs"></a><a name="afx_global_data__releasetaskbarrefs"></a> AFX_GLOBAL_DATA::ReleaseTaskBarRefs
Освобождает полученное через интерфейсы `GetITaskbarList` и `GetITaskbarList3` методы.  
  
  
```  
void ReleaseTaskBarRefs();
```  
  
## <a name="a-nameafxglobaldatashellcreateitemfromparsingnamea-afxglobaldatashellcreateitemfromparsingname"></a><a name="afx_global_data__shellcreateitemfromparsingname"></a> AFX_GLOBAL_DATA::ShellCreateItemFromParsingName
Создает и инициализирует объект элемента оболочки из имени синтаксического анализа.  
  
  
```  
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,  
    IBindCtx *pbc,  
    REFIID riid,  
    void **ppv);
```  
  
#### <a name="parameters"></a>Параметры  
 `pszPath`  
 [in] Указатель на отображаемое имя.  
  
 `pbc`  
 Указатель на контекст привязки, который управляет операции синтаксического анализа.  
  
 `riid`  
 Ссылку на идентификатор интерфейса.  
  
 `ppv`  
 [out] Когда эта функция возвращает значение, содержит указатель на интерфейс, запрошенный в `riid`. Обычно это будет `IShellItem` или `IShellItem2`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если выполнено успешно; в противном случае — значение ошибки.  

