---
title: "COleControl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleControl
dev_langs:
- C++
helpviewer_keywords:
- OLE controls, MFC
- windowless controls, MFC
- windowless controls
- controls [MFC], OLE
- controls [MFC], windowless
- COleControl class
ms.assetid: 53e95299-38e8-447b-9c5f-a381d27f5123
caps.latest.revision: 25
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
ms.openlocfilehash: 7ef5621aaf940be3ebe2806971dfc65d06972a5a
ms.lasthandoff: 02/24/2017

---
# <a name="colecontrol-class"></a>COleControl-класс
Мощный базовый класс для разработки элементов управления OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleControl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleControl::COleControl](#colecontrol)|Создает объект `COleControl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleControl::AmbientAppearance](#ambientappearance)|Получает текущий внешний вид элемента управления.|  
|[COleControl::AmbientBackColor](#ambientbackcolor)|Возвращает значение свойства BackColor окружения.|  
|[COleControl::AmbientDisplayName](#ambientdisplayname)|Возвращает имя элемента управления, как указано в качестве контейнера.|  
|[COleControl::AmbientFont](#ambientfont)|Возвращает значение свойства окружения шрифта.|  
|[COleControl::AmbientForeColor](#ambientforecolor)|Возвращает значение свойства ForeColor окружения.|  
|[COleControl::AmbientLocaleID](#ambientlocaleid)|Возвращает идентификатор языка контейнера.|  
|[COleControl::AmbientScaleUnits](#ambientscaleunits)|Возвращает тип единиц измерения, используемые контейнером.|  
|[COleControl::AmbientShowGrabHandles](#ambientshowgrabhandles)|Определяет, должны ли отображаться маркеры захвата.|  
|[COleControl::AmbientShowHatching](#ambientshowhatching)|Определяет, должны ли отображаться штриховки.|  
|[COleControl::AmbientTextAlign](#ambienttextalign)|Возвращает тип выравнивания текста, указанный в качестве контейнера.|  
|[COleControl::AmbientUIDead](#ambientuidead)|Определяет, если элемент управления должен отвечать на действия пользовательского интерфейса.|  
|[COleControl::AmbientUserMode](#ambientusermode)|Определяет режим контейнера.|  
|[COleControl::BoundPropertyChanged](#boundpropertychanged)|Уведомляет контейнера, что связанное свойство было изменено.|  
|[COleControl::BoundPropertyRequestEdit](#boundpropertyrequestedit)|Разрешение запросов на изменение значения свойства.|  
|[COleControl::ClientToParent](#clienttoparent)|Преобразует точку относительно начала координат элемента управления точку относительно начала координат его контейнера.|  
|[COleControl::ClipCaretRect](#clipcaretrect)|Корректирует прямоугольник курсора, если он перекрывается элементом управления.|  
|[COleControl::ControlInfoChanged](#controlinfochanged)|Эта функция вызывается после изменения набора мнемоник обрабатываться элементом управления.|  
|[COleControl::DisplayError](#displayerror)|Отображает события ошибки хранения пользователю элемента управления.|  
|[COleControl::DoClick](#doclick)|Реализация stock `DoClick` метод.|  
|[COleControl::DoPropExchange](#dopropexchange)|Сериализует свойства `COleControl` объекта.|  
|[COleControl::DoSuperclassPaint](#dosuperclasspaint)|Перерисовывает элемента управления OLE, подклассом элемента управления Windows Forms.|  
|[COleControl::EnableSimpleFrame](#enablesimpleframe)|Включает поддержку Простая рамка для элемента управления.|  
|[COleControl::ExchangeExtent](#exchangeextent)|Сериализует ширину и высоту элемента управления.|  
|[COleControl::ExchangeStockProps](#exchangestockprops)|Сериализует стандартных свойств элемента управления.|  
|[COleControl::ExchangeVersion](#exchangeversion)|Сериализует номер версии элемента управления.|  
|[COleControl::FireClick](#fireclick)|Запускает акции `Click` события.|  
|[COleControl::FireDblClick](#firedblclick)|Запускает акции `DblClick` события.|  
|[COleControl::FireError](#fireerror)|Запускает акции `Error` события.|  
|[COleControl::FireEvent](#fireevent)|Запускает пользовательское событие.|  
|[COleControl::FireKeyDown](#firekeydown)|Запускает акции `KeyDown` события.|  
|[COleControl::FireKeyPress](#firekeypress)|Запускает акции `KeyPress` события.|  
|[COleControl::FireKeyUp](#firekeyup)|Запускает акции `KeyUp` события.|  
|[COleControl::FireMouseDown](#firemousedown)|Запускает акции `MouseDown` события.|  
|[COleControl::FireMouseMove](#firemousemove)|Запускает акции `MouseMove` события.|  
|[COleControl::FireMouseUp](#firemouseup)|Запускает акции `MouseUp` события.|  
|[COleControl::FireReadyStateChange](#firereadystatechange)|Вызывает событие при изменении состояния готовности элемента управления.|  
|[COleControl::GetActivationPolicy](#getactivationpolicy)|Изменяет поведение активации по умолчанию элемент управления, поддерживающий `IPointerInactive` интерфейса.|  
|[COleControl::GetAmbientProperty](#getambientproperty)|Возвращает значение указанного свойства окружения.|  
|[COleControl::GetAppearance](#getappearance)|Возвращает значение стандартных свойств внешнего вида.|  
|[COleControl::GetBackColor](#getbackcolor)|Возвращает значение свойству BackColor акций.|  
|[COleControl::GetBorderStyle](#getborderstyle)|Возвращает значение свойства BorderStyle акций.|  
|[COleControl::GetCapture](#getcapture)|Определяет, имеет ли объект элемента управления без окон, активированные захвата мыши.|  
|[COleControl::GetClassID](#getclassid)|Извлекает идентификатор класса элемента управления OLE.|  
|[COleControl::GetClientOffset](#getclientoffset)|Возвращает разницу между левом верхнем углу прямоугольной области элемента управления и верхней левой части клиентской области.|  
|[COleControl::GetClientRect](#getclientrect)|Возвращает размер клиентской области элемента управления.|  
|[COleControl::GetClientSite](#getclientsite)|Запрашивает объект для указателя на текущий сайт клиента в пределах своего контейнера.|  
|[COleControl::GetControlFlags](#getcontrolflags)|Извлекает параметры управления флаг.|  
|[COleControl::GetControlSize](#getcontrolsize)|Возвращает положение и размер элемента управления OLE.|  
|[COleControl::GetDC](#getdc)|Предоставляет средства для безоконный элемент управления для получения контекста устройства из контейнера.|  
|[COleControl::GetEnabled](#getenabled)|Возвращает значение свойства Enabled акции.|  
|[COleControl::GetExtendedControl](#getextendedcontrol)|Извлекает указатель на объект расширенного элемента управления, относящиеся к контейнеру.|  
|[COleControl::GetFocus](#getfocus)|Определяет, является ли элемент управления имеет фокус.|  
|[COleControl::GetFont](#getfont)|Возвращает значение свойство Font.|  
|[COleControl::GetFontTextMetrics](#getfonttextmetrics)|Возвращает показатели из `CFontHolder` объекта.|  
|[COleControl::GetForeColor](#getforecolor)|Возвращает значение свойства ForeColor акций.|  
|[COleControl::GetHwnd](#gethwnd)|Возвращает значение свойства акций hWnd.|  
|[COleControl::GetMessageString](#getmessagestring)|Содержит текст строки состояния для элемента меню.|  
|[COleControl::GetNotSupported](#getnotsupported)|Запрещает доступ к значению свойства элемента управления для пользователя.|  
|[COleControl::GetReadyState](#getreadystate)|Возвращает состояние готовности элемента управления.|  
|[COleControl::GetRectInContainer](#getrectincontainer)|Возвращает прямоугольник элемента управления относительно его контейнера.|  
|[COleControl::GetStockTextMetrics](#getstocktextmetrics)|Возвращает показатели свойство Font.|  
|[COleControl::GetText](#gettext)|Возвращает значение стандартное свойство Text или Caption.|  
|[COleControl::GetWindowlessDropTarget](#getwindowlessdroptarget)|Переопределите, чтобы разрешить безоконный элемент управления быть целевым объектом перетаскивания и операции перетаскивания.|  
|[COleControl::InitializeIIDs](#initializeiids)|Информирует о базовом классе IID, элемент управления будет использовать.|  
|[COleControl::InternalGetFont](#internalgetfont)|Возвращает `CFontHolder` свойство Font объекта.|  
|[COleControl::InternalGetText](#internalgettext)|Извлекает заголовок или текст свойство.|  
|[COleControl::InternalSetReadyState](#internalsetreadystate)|Задает состояние готовности элемента управления и вызывает событие изменения состояния готовности.|  
|[COleControl::InvalidateControl](#invalidatecontrol)|Делает недействительной область отображаемого элемента управления, вызывает его перерисовку.|  
|[COleControl::InvalidateRgn](#invalidatergn)|Делает недействительным окно контейнера клиентской области в пределах данной области. Можно использовать для повторной отрисовки без окон элементов управления в области.|  
|[COleControl::IsConvertingVBX](#isconvertingvbx)|Разрешает специализированные загрузку элемента управления OLE.|  
|[COleControl::IsModified](#ismodified)|Определяет, изменилась ли состояние элемента управления.|  
|[COleControl::IsOptimizedDraw](#isoptimizeddraw)|Указывает, поддерживает ли контейнер оптимизированного рисования для текущей операции рисования.|  
|[COleControl::IsSubclassedControl](#issubclassedcontrol)|Вызывается, чтобы определить, если управление подклассов элементов управления Windows.|  
|[COleControl::Load](#load)|Сбрасывает любых предыдущих асинхронных данных и инициализирует новую загрузку асинхронного свойства элемента управления.|  
|[COleControl::LockInPlaceActive](#lockinplaceactive)|Определяет, если элемент управления могут быть деактивированы путем контейнера.|  
|[COleControl::OnAmbientPropertyChange](#onambientpropertychange)|Вызывается при изменении свойств окружения.|  
|[COleControl::OnAppearanceChanged](#onappearancechanged)|Вызывается при изменении стандартных свойств внешнего вида.|  
|[COleControl::OnBackColorChanged](#onbackcolorchanged)|Вызывается, когда изменяется свойство BackColor.|  
|[COleControl::OnBorderStyleChanged](#onborderstylechanged)|Вызывается, когда изменяется свойство BorderStyle.|  
|[COleControl::OnClick](#onclick)|Вызывается срабатывание акции щелкните событие.|  
|[COleControl::OnClose](#onclose)|Уведомляет элемент управления, `IOleControl::Close` был вызван.|  
|[COleControl::OnDoVerb](#ondoverb)|Вызывается после выполнения команды управления.|  
|[COleControl::OnDraw](#ondraw)|Вызывается, когда элемент запрашивается перерисовывает себя.|  
|[COleControl::OnDrawMetafile](#ondrawmetafile)|Вызывается контейнером при запросе элемента управления перерисовка использование контекста устройства метафайла.|  
|[COleControl::OnEdit](#onedit)|Вызывается контейнером для активации пользовательского интерфейса элемента управления OLE.|  
|[COleControl::OnEnabledChanged](#onenabledchanged)|Вызывается при изменении свойства Enabled акции.|  
|[COleControl::OnEnumVerbs](#onenumverbs)|Вызывается контейнером для перечисления команд элементов управления.|  
|[COleControl::OnEventAdvise](#oneventadvise)|Вызывается, когда обработчики событий или вынимается из элемента управления.|  
|[COleControl::OnFontChanged](#onfontchanged)|Вызывается, когда изменяется свойство Font.|  
|[COleControl::OnForeColorChanged](#onforecolorchanged)|Вызывается, когда изменяется свойство цвет переднего плана.|  
|[COleControl::OnFreezeEvents](#onfreezeevents)|Вызывается, когда события элемента управления зафиксированное или снять состояние фиксации.|  
|[COleControl::OnGetColorSet](#ongetcolorset)|Уведомляет элемент управления, `IOleObject::GetColorSet` был вызван.|  
|[COleControl::OnGetControlInfo](#ongetcontrolinfo)|Назначенный сведения о контейнере.|  
|[COleControl::OnGetDisplayString](#ongetdisplaystring)|Вызывается для получения строки для представления значения свойства.|  
|[COleControl::OnGetInPlaceMenu](#ongetinplacemenu)|Запрашивает дескриптор элемента управления меню будут объединены с меню контейнера.|  
|[COleControl::OnGetNaturalExtent](#ongetnaturalextent)|Переопределение для получения ближайший к предложенный режим размера и степени размер отображения элемента управления.|  
|[COleControl::OnGetPredefinedStrings](#ongetpredefinedstrings)|Возвращает строки, представляющие возможные значения для свойства.|  
|[COleControl::OnGetPredefinedValue](#ongetpredefinedvalue)|Возвращает значение, соответствующее заранее определенную строку.|  
|[COleControl::OnGetViewExtent](#ongetviewextent)|Переопределите, чтобы получить размер областей отображения элемента управления (может использоваться для включения Рисование два прохода).|  
|[COleControl::OnGetViewRect](#ongetviewrect)|Переопределение, чтобы преобразовать размер элемента управления в прямоугольник, начиная с указанной позиции.|  
|[COleControl::OnGetViewStatus](#ongetviewstatus)|Переопределение, чтобы получить состояние представления элемента управления.|  
|[COleControl::OnHideToolBars](#onhidetoolbars)|Вызывается контейнером при деактивации пользовательского интерфейса элемента управления.|  
|[COleControl::OnInactiveMouseMove](#oninactivemousemove)|Переопределение, чтобы иметь контейнер для неактивный элемент управления в группе диспетчеризации указатель мыши `WM_MOUSEMOVE` сообщений для элемента управления.|  
|[COleControl::OnInactiveSetCursor](#oninactivesetcursor)|Переопределение, чтобы иметь контейнер для неактивный элемент управления в группе диспетчеризации указатель мыши `WM_SETCURSOR` сообщений для элемента управления.|  
|[COleControl::OnKeyDownEvent](#onkeydownevent)|Вызывается после возникло событие KeyDown акций.|  
|[COleControl::OnKeyPressEvent](#onkeypressevent)|Вызывается после возникло событие KeyPress акций.|  
|[COleControl::OnKeyUpEvent](#onkeyupevent)|Вызывается после возникло событие KeyUp акций.|  
|[COleControl::OnMapPropertyToPage](#onmappropertytopage)|Указывает, какую страницу свойств для редактирования свойства.|  
|[COleControl::OnMnemonic](#onmnemonic)|Вызывается, когда была нажата назначенная клавиша элемента управления.|  
|[COleControl::OnProperties](#onproperties)|Вызывается при вызове команды «Свойства» элемента управления.|  
|[COleControl::OnQueryHitPoint](#onqueryhitpoint)|Переопределить запрос ли заданная точка перекрывается отображение элемента управления.|  
|[COleControl::OnQueryHitRect](#onqueryhitrect)|Переопределить запрос ли отображение элемента управления перекрывается любую точку в данном прямоугольнике.|  
|[COleControl::OnRenderData](#onrenderdata)|Вызывается платформой для получения данных в указанном формате.|  
|[COleControl::OnRenderFileData](#onrenderfiledata)|Вызывается платформой для извлечения данных из файла в указанном формате.|  
|[COleControl::OnRenderGlobalData](#onrenderglobaldata)|Вызывается платформой для извлечения данных из глобальной памяти в указанном формате.|  
|[COleControl::OnResetState](#onresetstate)|Сброс свойств элемента управления значения по умолчанию.|  
|[COleControl::OnSetClientSite](#onsetclientsite)|Уведомляет элемент управления, `IOleControl::SetClientSite` был вызван.|  
|[COleControl::OnSetData](#onsetdata)|Заменяет элемент управления данными с другим значением.|  
|[COleControl::OnSetExtent](#onsetextent)|Вызывается после изменения расширения элемента управления.|  
|[COleControl::OnSetObjectRects](#onsetobjectrects)|Вызывается после были изменены размеры элемента управления.|  
|[COleControl::OnShowToolBars](#onshowtoolbars)|Вызывается, когда элемент был активирован пользовательского интерфейса.|  
|[COleControl::OnTextChanged](#ontextchanged)|Вызывается при изменении акций текст или свойства Caption.|  
|[COleControl::OnWindowlessMessage](#onwindowlessmessage)|Обрабатывает сообщения окна (кроме сообщения клавиатуры и мыши) для элементов управления без окон.|  
|[COleControl::ParentToClient](#parenttoclient)|Преобразует точку относительно контейнера источника на момент относительно начала координат элемента управления.|  
|[COleControl::PostModalDialog](#postmodaldialog)|Уведомляет контейнера закрыт модального диалогового окна.|  
|[COleControl::PreModalDialog](#premodaldialog)|Уведомляет контейнер, в котором модального диалогового окна будет отображаться.|  
|[COleControl::RecreateControlWindow](#recreatecontrolwindow)|Удаляет и повторно создает окна элемента управления.|  
|[COleControl::Refresh](#refresh)|Вызывает принудительную закраску внешнего вида элемента управления.|  
|[COleControl::ReleaseCapture](#releasecapture)|Освобождает захват мыши.|  
|[COleControl::ReleaseDC](#releasedc)|Освобождает контекст устройства отображения контейнера безоконный элемент управления.|  
|[COleControl::ReparentControlWindow](#reparentcontrolwindow)|Сбрасывает родительского окна элемента управления.|  
|[COleControl::ResetStockProps](#resetstockprops)|Инициализирует `COleControl` стандартные свойства до значений по умолчанию.|  
|[COleControl::ResetVersion](#resetversion)|Инициализирует номер версии для заданного значения.|  
|[COleControl::ScrollWindow](#scrollwindow)|Позволяет безоконный элемент управления для прокрутки области в ее на месте активного изображения на экране.|  
|[COleControl::SelectFontObject](#selectfontobject)|Выбор пользовательского свойства шрифта в контексте устройства.|  
|[COleControl::SelectStockFont](#selectstockfont)|Выбирает свойство Font в контексте устройства.|  
|[COleControl::SerializeExtent](#serializeextent)|Сериализует или инициализирует область отображения элемента управления.|  
|[COleControl::SerializeStockProps](#serializestockprops)|Сериализует или инициализирует `COleControl` стандартные свойства.|  
|[COleControl::SerializeVersion](#serializeversion)|Сериализует или инициализирует сведения о версии элемента управления.|  
|[COleControl::SetAppearance](#setappearance)|Задает значение стандартных свойств внешнего вида.|  
|[COleControl::SetBackColor](#setbackcolor)|Задает значение свойству BackColor акций.|  
|[COleControl::SetBorderStyle](#setborderstyle)|Задает значение свойства BorderStyle акций.|  
|[COleControl::SetCapture](#setcapture)|В результате окна контейнера элемента управления необходимо выполнить владения захвата мыши на имени элемента управления.|  
|[COleControl::SetControlSize](#setcontrolsize)|Задает положение и размер элемента управления OLE.|  
|[COleControl::SetEnabled](#setenabled)|Задает значение свойства Enabled акции.|  
|[COleControl::SetFocus](#setfocus)|В результате элемент управления контейнера окно владение фокус ввода от имени элемента управления.|  
|[COleControl::SetFont](#setfont)|Задает значение свойство Font.|  
|[COleControl::SetForeColor](#setforecolor)|Задает значение свойства ForeColor акций.|  
|[COleControl::SetInitialSize](#setinitialsize)|Задает размер элемента управления OLE, при первом отображении в контейнере.|  
|[COleControl::SetModifiedFlag](#setmodifiedflag)|Изменяет измененном состоянии элемента управления.|  
|[COleControl::SetNotPermitted](#setnotpermitted)|Указывает, что произошел сбой запроса на изменение.|  
|[COleControl::SetNotSupported](#setnotsupported)|Предотвращает изменение значения свойства элемента управления для пользователя.|  
|[COleControl::SetRectInContainer](#setrectincontainer)|Задает прямоугольник элемента управления относительно его контейнера.|  
|[COleControl::SetText](#settext)|Задает значение текста или заголовка свойство.|  
|[COleControl::ThrowError](#throwerror)|Указывает, произошла ошибка в элементе управления OLE.|  
|[COleControl::TransformCoords](#transformcoords)|Значения между контейнером и управления координат преобразований.|  
|[COleControl::TranslateColor](#translatecolor)|Преобразует **OLE_COLOR** значение **COLORREF** значение.|  
|[COleControl::WillAmbientsBeValidDuringLoad](#willambientsbevalidduringload)|Определяет свойства окружения ли доступны при очередном элемент управления будет загружен.|  
|[COleControl::WindowProc](#windowproc)|Содержит процедуры Windows `COleControl` объекта.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleControl::DrawContent](#drawcontent)|Вызывается платформой, когда внешний вид элемента управления должен быть обновлен.|  
|[COleControl::DrawMetafile](#drawmetafile)|Вызывается инфраструктурой при использовании контекста устройства метафайла.|  
|[COleControl::IsInvokeAllowed](#isinvokeallowed)|Включает вызов метода автоматизации.|  
|[COleControl::SetInitialDataFormats](#setinitialdataformats)|Вызывается платформой для инициализации список форматов данных, поддерживаемый данным элементом управления.|  
  
## <a name="remarks"></a>Примечания  
 Производный от `CWnd`, этот класс наследует все функциональные возможности объекта окна Windows, а также дополнительные функциональные возможности, связанные с OLE, например события Click и возможность поддержки методы и свойства.  
  
 Элементы управления OLE могут быть вставлены в OLE-приложения контейнера и взаимодействовать с контейнером, с помощью двустороннее системы события Click и предоставление методов и свойств в контейнер. Обратите внимание, что стандартная OLE-контейнеры поддерживают основные функциональные возможности элемента управления OLE. Они не поддерживают расширенные функциональные возможности элемента управления OLE. Событие возникает, когда события отправляются в контейнер, в результате некоторые действия, происходящие в элементе управления. В свою очередь контейнер взаимодействует с элементом управления, используя предоставленный набор методов и свойств, аналогична функции-члены и члены данных класса C++. Такой подход позволяет разработчику управлять внешним видом элемента управления и уведомить контейнера при возникновении определенных действий.  
  
## <a name="windowless-controls"></a>Элементы управления без окон  
 Элементы управления OLE может быть используется активным на месте без окна. Безоконный элементы управления имеют значительные преимущества.  
  
-   Элементы управления без окон может быть прозрачной и непрямоугольных  
  
-   Элементы управления без окон снизить экземпляр размер и время создания объекта  
  
 Элементы управления окна не требуется. Службы, доступные в окне легко могут быть предоставлены через одного общего окна (обычно контейнера) и немного кода диспетчеризации. Окно является главным образом это ненужное усложнение объекта.  
  
 При использовании активации без окна контейнер (имеет окна) отвечает за предоставление служб, которые бы в противном случае были предоставлены с помощью элемента управления собственные окна. Например если элемент управления должен запрашивать фокус клавиатуры, запрос на захват мыши или получить контекст устройства, эти операции осуществляется с помощью контейнера. `COleControl` [Функции-члены безоконный операции](http://msdn.microsoft.com/en-us/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) вызова этих операций в контейнере.  
  
 При включении активации без окна делегаты контейнер входных сообщений для элемента управления `IOleInPlaceObjectWindowless` интерфейса (расширение [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) безоконный поддержки). `COleControl`в реализации этого интерфейса отправляет эти сообщения через схему сообщений для элемента управления, после настройки мыши координирует соответствующим образом. Можно обработать эти сообщения как обычный оконных сообщений, добавив соответствующие записи в схеме сообщений.  
  
 Безоконный элемент управления, следует всегда использовать `COleControl` вместо соответствующих функций-членов `CWnd` функции-члены и их связанные функции Windows API.  
  
 Элемент управления OLE-объекты можно также создать окно только в том случае, когда они становятся активными, но возрастает объем работы, необходимый для неактивных активный переход и скорость перехода выходит из строя. Бывают случаи, когда это проблема: в качестве примера рассмотрим сетка текстовых полей. Когда курсора вверх и вниз по столбцу каждого элемента управления должны быть на месте активируется и деактивируется затем. Скорость перехода неактивные активный непосредственно влияют на скорость прокрутки.  
  
 Дополнительные сведения о разработке платформу управления OLE, см. в статьях [элементы управления ActiveX MFC](../../mfc/mfc-activex-controls.md) и [Обзор: создание программы управления MFC ActiveX](../../mfc/reference/mfc-activex-control-wizard.md). Сведения по оптимизации элементов управления OLE, включая элементы управления без окон и мерцания см [элементы управления ActiveX в MFC: оптимизация](../../mfc/mfc-activex-controls-optimization.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `COleControl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h  
  
##  <a name="a-nameambientbackcolora--colecontrolambientbackcolor"></a><a name="ambientbackcolor"></a>COleControl::AmbientBackColor  
 Возвращает значение свойства BackColor окружения.  
  
```  
OLE_COLOR AmbientBackColor();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение контейнера окружения значение свойству BackColor, если таковые имеются. Если свойство не поддерживается, эта функция возвращает цвет фона определяемые системой Windows.  
  
### <a name="remarks"></a>Примечания  
 Свойство BackColor окружения доступна для всех элементов управления и определяется в контейнере. Обратите внимание, что контейнер не требуется для поддержки этого свойства.  
  
##  <a name="a-nameambientdisplaynamea--colecontrolambientdisplayname"></a><a name="ambientdisplayname"></a>COleControl::AmbientDisplayName  
 Имя контейнера назначенный элементу управления можно использовать в сообщениях об ошибках, отображаемых для пользователя.  
  
```  
CString AmbientDisplayName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя элемента управления OLE. Значение по умолчанию — пустая строка.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что контейнер не требуется для поддержки этого свойства.  
  
##  <a name="a-nameambientfonta--colecontrolambientfont"></a><a name="ambientfont"></a>COleControl::AmbientFont  
 Возвращает значение свойства окружения шрифта.  
  
```  
LPFONTDISP AmbientFont();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс диспетчеризации окружения шрифт контейнера. Значение по умолчанию — **NULL**. Если возврат не равен **NULL**, вы несете ответственность за освобождение шрифта, вызвав его [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) функции-члена.  
  
### <a name="remarks"></a>Примечания  
 Внешнее свойство шрифта определяется контейнер и доступны для всех элементов управления. Обратите внимание, что контейнер не требуется для поддержки этого свойства.  
  
##  <a name="a-nameambientforecolora--colecontrolambientforecolor"></a><a name="ambientforecolor"></a>COleControl::AmbientForeColor  
 Возвращает значение свойства ForeColor окружения.  
  
```  
OLE_COLOR AmbientForeColor();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение контейнера ForeColor свойств окружения, если таковые имеются. Если не поддерживается, эта функция возвращает цвет текста определяемые системой Windows.  
  
### <a name="remarks"></a>Примечания  
 Внешнее свойство ForeColor доступна для всех элементов управления и определяется в контейнере. Обратите внимание, что контейнер не требуется для поддержки этого свойства.  
  
##  <a name="a-nameambientlocaleida--colecontrolambientlocaleid"></a><a name="ambientlocaleid"></a>COleControl::AmbientLocaleID  
 Возвращает идентификатор языка контейнера.  
  
```  
LCID AmbientLocaleID();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение свойства контейнера LocaleID, при их наличии. Если это свойство не поддерживается, эта функция возвращает 0.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления можно использовать код языка адаптировать его пользовательский интерфейс для конкретных языков. Обратите внимание, что контейнер не требуется для поддержки этого свойства.  
  
##  <a name="a-nameambientappearancea--colecontrolambientappearance"></a><a name="ambientappearance"></a>COleControl::AmbientAppearance  
 Извлекает текущую настройку внешнего вида объекта управления.  
  
```  
short AmbientAppearance();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Внешний вид элемента управления:  
  
- **0** плоский внешний вид  
  
- **1** трехмерного вида  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения текущего значения **DISPID_AMBIENT_APPEARANCE** для элемента управления.  
  
##  <a name="a-nameambientscaleunitsa--colecontrolambientscaleunits"></a><a name="ambientscaleunits"></a>COleControl::AmbientScaleUnits  
 Возвращает тип единиц измерения, используемые контейнером.  
  
```  
CString AmbientScaleUnits();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая окружения ScaleUnits контейнера. Если это свойство не поддерживается, эта функция возвращает строку нулевой длины.  
  
### <a name="remarks"></a>Примечания  
 Внешнее свойство ScaleUnits контейнера можно использовать для отображения позиций или измерений, помеченные для выбранного подразделения, например твипов или сантиметры. Обратите внимание, что контейнер не требуется для поддержки этого свойства.  
  
##  <a name="a-nameambientshowgrabhandlesa--colecontrolambientshowgrabhandles"></a><a name="ambientshowgrabhandles"></a>COleControl::AmbientShowGrabHandles  
 Определяет, позволяет ли контейнер элемента управления для отображения ручки для себя, когда активны.  
  
```  
BOOL AmbientShowGrabHandles();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если должны отображаться маркеры захвата; в противном случае — 0. Если это свойство не поддерживается, эта функция возвращает ненулевое значение.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что контейнер не требуется для поддержки этого свойства.  
  
##  <a name="a-nameambientshowhatchinga--colecontrolambientshowhatching"></a><a name="ambientshowhatching"></a>COleControl::AmbientShowHatching  
 Определяет, позволяет ли контейнер элемента управления для отображения самого с заштрихованного шаблон, если активный пользовательского интерфейса.  
  
```  
BOOL AmbientShowHatching();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если необходимо отобразить заштрихованного шаблон; в противном случае — 0. Если это свойство не поддерживается, эта функция возвращает ненулевое значение.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что контейнер не требуется для поддержки этого свойства.  
  
##  <a name="a-nameambienttextaligna--colecontrolambienttextalign"></a><a name="ambienttextalign"></a>COleControl::AmbientTextAlign  
 Определяет выравнивание текста окружения, предпочтительным контейнером элемента управления.  
  
```  
short AmbientTextAlign();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние свойства TextAlign окружения контейнера. Если это свойство не поддерживается, эта функция возвращает 0.  
  
 Ниже приведен список допустимых значений для возврата.  
  
|Возвращаемое значение|Значение|  
|------------------|-------------|  
|0|Обычное выравнивание (номера для текста справа, слева).|  
|1|Выравнивание по левому краю|  
|2|Center|  
|3|Выравнивание по правому краю|  
  
### <a name="remarks"></a>Примечания  
 Это свойство доступно для всех внедренных элементов управления и определяется в контейнере. Обратите внимание, что контейнер не требуется для поддержки этого свойства.  
  
##  <a name="a-nameambientuideada--colecontrolambientuidead"></a><a name="ambientuidead"></a>COleControl::AmbientUIDead  
 Определяет, если контейнер хочет управления реагировать на действия пользовательского интерфейса.  
  
```  
BOOL AmbientUIDead();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления должен отвечать на действия пользовательского интерфейса. в противном случае — 0. Если это свойство не поддерживается, эта функция возвращает 0.  
  
### <a name="remarks"></a>Примечания  
 Например, контейнер может присвоить это **TRUE** в режиме конструктора.  
  
##  <a name="a-nameambientusermodea--colecontrolambientusermode"></a><a name="ambientusermode"></a>COleControl::AmbientUserMode  
 Определяет, является ли контейнер в режиме конструктора или в режиме пользователя.  
  
```  
BOOL AmbientUserMode();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если контейнер является в пользовательском режиме; в противном случае — 0 (в режиме конструктора). Если это свойство не поддерживается, эта функция возвращает значение TRUE.  
  
### <a name="remarks"></a>Примечания  
 Например, контейнер может присвоить это **FALSE** в режиме конструктора.  
  
##  <a name="a-nameboundpropertychangeda--colecontrolboundpropertychanged"></a><a name="boundpropertychanged"></a>COleControl::BoundPropertyChanged  
 Указывает, что изменилось значение свойства привязки.  
  
```  
void BoundPropertyChanged(DISPID dispid);
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации связанных свойств элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Это должно вызываться каждый раз при изменении свойства даже в тех случаях, когда не было внесено изменение через свойство значение метода. Помните, особенно связанных свойств, которые сопоставлены с переменными-членами. Такой член изменения переменных, в любое время `BoundPropertyChanged` должен вызываться.  
  
##  <a name="a-nameboundpropertyrequestedita--colecontrolboundpropertyrequestedit"></a><a name="boundpropertyrequestedit"></a>COleControl::BoundPropertyRequestEdit  
 Запрашивает разрешение у `IPropertyNotifySink` интерфейс для изменения значения свойства привязки, предоставляемые элементом управления.  
  
```  
BOOL BoundPropertyRequestEdit(DISPID dispid);
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации связанных свойств элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если изменение разрешено; в противном случае — 0. Значение по умолчанию — ненулевое значение.  
  
### <a name="remarks"></a>Примечания  
 Если разрешения, элемент управления не должен позволять значение изменения свойства. Это можно сделать, игнорируя или сбой действия, которое была предпринята попытка изменить значение свойства.  
  
##  <a name="a-nameclienttoparenta--colecontrolclienttoparent"></a><a name="clienttoparent"></a>COleControl::ClientToParent  
 Преобразует координаты `pPoint` в родительских координатах.  
  
```  
virtual void ClientToParent(
    LPCRECT lprcBounds, 
    LPPOINT pPoint) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lprcBounds`  
 Указатель на границы элемента управления OLE в контейнере. Области всего элемента управления, включая границами и полосами прокрутки, но не клиентской области.  
  
 `pPoint`  
 Указатель на точку области клиента OLE было преобразовано в координатах родительского элемента (контейнер).  
  
### <a name="remarks"></a>Примечания  
 На входе `pPoint` относительно начала координат клиентской области элемента управления OLE (верхний левый угол клиентской области элемента управления). На выходе `pPoint` относительно начала координат родительского объекта (верхний левый угол контейнера).  
  
##  <a name="a-nameclipcaretrecta--colecontrolclipcaretrect"></a><a name="clipcaretrect"></a>COleControl::ClipCaretRect  
 Корректирует прямоугольник курсор, если он полностью или частично охваченные непрозрачных перекрывающихся объектов.  
  
```  
BOOL ClipCaretRect(LPRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 На входной указатель [RECT](../../mfc/reference/rect-structure1.md) структуру, содержащую курсор области скорректирована. На выходе области скорректированной курсора или **NULL** если прямоугольник курсор полностью поддерживается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Мигающий линии, блока или точечного рисунка, обычно указывает на место будет вставлен текст или рисунок находится курсор.  
  
 Безоконный объекта невозможно безопасно отобразить курсор без проверки ли курсор будет частично или полностью скрыт перекрывающихся объектов. Для этого можно использовать объект `ClipCaretRect` для получения курсора изменены (сокращенный) чтобы он поместился в области отсечения.  
  
 Объекты, создание курсор должен отправить прямоугольника, курсор `ClipCaretRect` и использовать прямоугольник, настроенная для курсора. Если курсор полностью скрыт, этот метод вернет **FALSE** и курсор не должен отображаться вообще в этом случае.  
  
##  <a name="a-namecolecontrola--colecontrolcolecontrol"></a><a name="colecontrol"></a>COleControl::COleControl  
 Создает объект `COleControl`.  
  
```  
COleControl();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно не вызывается напрямую. Вместо этого элемент управления OLE обычно создается путем его фабрики класса.  
  
##  <a name="a-namecontrolinfochangeda--colecontrolcontrolinfochanged"></a><a name="controlinfochanged"></a>COleControl::ControlInfoChanged  
 Эта функция вызывается при изменении набора из мнемоник, поддерживаемый данным элементом управления.  
  
```  
void ControlInfoChanged();
```  
  
### <a name="remarks"></a>Примечания  
 При получении уведомления, контейнер элемента управления получает новый набор из мнемоник, делая вызов к [IOleControl::GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730). Обратите внимание, что контейнер не требуется ответить на это уведомление.  
  
##  <a name="a-namedisplayerrora--colecontroldisplayerror"></a><a name="displayerror"></a>COleControl::DisplayError  
 Вызывается платформой после обработки биржевых события ошибки (если обработчик события заблокировал отображение ошибки).  
  
```  
virtual void DisplayError(
    SCODE scode,  
    LPCTSTR lpszDescription,  
    LPCTSTR lpszSource,  
    LPCTSTR lpszHelpFile,  
    UINT nHelpID);
```  
  
### <a name="parameters"></a>Параметры  
 *SCODE*  
 Значение кода состояния для создания отчета. Полный список возможных кодов см. в статье [элементы управления ActiveX: Дополнительные темы](../../mfc/mfc-activex-controls-advanced-topics.md).  
  
 `lpszDescription`  
 Описание сообщение об ошибке.  
  
 *lpszSource*  
 Имя модуля, вызвавшего ошибку (как правило, имя модуля управления OLE).  
  
 `lpszHelpFile`  
 Имя файла справки, содержащий описание ошибки.  
  
 `nHelpID`  
 Идентификатор контекста справки ошибки сообщается.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию отображает окно сообщения, содержащего описание ошибки, содержащихся в `lpszDescription`.  
  
 Переопределите эту функцию, чтобы настроить способ отображения ошибок.  
  
##  <a name="a-namedoclicka--colecontroldoclick"></a><a name="doclick"></a>COleControl::DoClick  
 Имитирует мыши выберите действие на элементе управления.  
  
```  
void DoClick();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределяемый `COleControl::OnClick` будет вызываться функция-член и щелкните событие инициируется, если поддерживается элементом управления.  
  
 Эта функция поддерживается `COleControl` базового класса как акций метод, именуемый DoClick. Дополнительные сведения см. в статье [элементы управления ActiveX: методы](../../mfc/mfc-activex-controls-methods.md).  
  
##  <a name="a-namedopropexchangea--colecontroldopropexchange"></a><a name="dopropexchange"></a>COleControl::DoPropExchange  
 Вызывается средой во время загрузки или сохранения элемента управления из представления постоянное хранилище, например поток или свойство набора.  
  
```  
virtual void DoPropExchange(CPropExchange* pPX);
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на объект `CPropExchange`. Инфраструктура предоставляет этот объект используется для определения контекста свойство exchange, включая его направление.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывает **PX_** семейство функций, загрузку и сохранение пользовательских свойств элемента управления OLE.  
  
 Если мастер элементов управления позволяет создать проект элемента управления OLE, переопределенная версия этой функции будет сериализовать стандартных свойств, поддерживаемых `COleControl` с помощью вызова функции базового класса `COleControl::DoPropExchange`. При добавлении пользовательских свойств будет необходимо изменить эту функцию для сериализации нового свойства элемента управления OLE. Дополнительные сведения о сериализации см. в статье [элементы управления ActiveX: сериализации](../../mfc/mfc-activex-controls-serializing.md).  
  
##  <a name="a-namedosuperclasspainta--colecontroldosuperclasspaint"></a><a name="dosuperclasspaint"></a>COleControl::DoSuperclassPaint  
 Перерисовывает элемента управления OLE, подклассом элемента управления Windows Forms.  
  
```  
void DoSuperclassPaint(
    CDC* pDC,  
    const CRect& rcBounds);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства контейнера элемента управления.  
  
 `rcBounds`  
 Область, в котором будет отображаться элемент управления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для правильной обработки заливку неактивную управления OLE. Эту функцию следует использовать, только если OLE управления подклассы Windows и должен быть вызван в `OnDraw` функции элемента управления.  
  
 Дополнительные сведения о функции и создание подкласса элемента управления Windows, см. в статье [элементы управления ActiveX: Создание подкласса элемента управления Windows](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
##  <a name="a-namedrawcontenta--colecontroldrawcontent"></a><a name="drawcontent"></a>COleControl::DrawContent  
 Вызывается платформой, когда внешний вид элемента управления должен быть обновлен.  
  
```  
void DrawContent(
    CDC* pDC,  
    CRect& rc);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства.  
  
 `rc`  
 Прямоугольная область для отображения.  
  
### <a name="remarks"></a>Примечания  
 Эта функция напрямую вызывает переопределяемый `OnDraw` функции.  
  
##  <a name="a-namedrawmetafilea--colecontroldrawmetafile"></a><a name="drawmetafile"></a>COleControl::DrawMetafile  
 Вызывается инфраструктурой при использовании контекста устройства метафайла.  
  
```  
void DrawMetafile(
    CDC* pDC,  
    CRect& rc);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства метафайла.  
  
 `rc`  
 Прямоугольная область для отображения.  
  
##  <a name="a-nameenablesimpleframea--colecontrolenablesimpleframe"></a><a name="enablesimpleframe"></a>COleControl::EnableSimpleFrame  
 Позволяет характеристика Простая рамка для элемента управления OLE.  
  
```  
void EnableSimpleFrame();
```  
  
### <a name="remarks"></a>Примечания  
 Эта характеристика позволяет элементу управления для поддержки visual вложения других элементов управления, но не true вложения OLE. Примером служит поле с несколькими элементами управления внутри группы. Эти элементы управления не содержится OLE, но они находятся в одном поле группы.  
  
##  <a name="a-nameexchangeextenta--colecontrolexchangeextent"></a><a name="exchangeextent"></a>COleControl::ExchangeExtent  
 Сериализует или инициализирует состояние область элемента управления (его измерений в **HIMETRIC** единиц).  
  
```  
BOOL ExchangeExtent(CPropExchange* pPX);
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта. Инфраструктура предоставляет этот объект используется для определения контекста свойство exchange, включая его направление.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается реализация по умолчанию `COleControl::DoPropExchange`.  
  
##  <a name="a-nameexchangestockpropsa--colecontrolexchangestockprops"></a><a name="exchangestockprops"></a>COleControl::ExchangeStockProps  
 Сериализует или инициализирует состояние стандартных свойств элемента управления.  
  
```  
void ExchangeStockProps(CPropExchange* pPX);
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта. Инфраструктура предоставляет этот объект используется для определения контекста свойство exchange, включая его направление.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается реализация по умолчанию `COleControl::DoPropExchange`.  
  
##  <a name="a-nameexchangeversiona--colecontrolexchangeversion"></a><a name="exchangeversion"></a>COleControl::ExchangeVersion  
 Сериализует или инициализирует состояние сведения о версии элемента управления.  
  
```  
BOOL ExchangeVersion(
    CPropExchange* pPX,  
    DWORD dwVersionDefault,  
    BOOL bConvert = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на объект `CPropExchange`. Инфраструктура предоставляет этот объект используется для определения контекста свойство exchange, включая его направление.  
  
 `dwVersionDefault`  
 Номер текущей версии элемента управления.  
  
 `bConvert`  
 Указывает, следует ли преобразовывать в формат последней версии при сохранении или сохраняется в том же формате, который был загружен постоянных данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Как правило, это будет Первая функция вызывается переопределение элемента управления `COleControl::DoPropExchange`. При загрузке, эта функция считывает номер версии постоянных данных и задает атрибуту версии [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта соответствующим образом. При сохранении, эта функция записывает номер версии постоянных данных.  
  
 Дополнительные сведения о сохраняемости и управления версиями см. в статье [элементы управления ActiveX: сериализации](../../mfc/mfc-activex-controls-serializing.md).  
  
##  <a name="a-namefireclicka--colecontrolfireclick"></a><a name="fireclick"></a>COleControl::FireClick  
 Вызывается инфраструктурой при щелчке мышью по активным элементом управления.  
  
```  
void FireClick();
```  
  
### <a name="remarks"></a>Примечания  
 Если оно определено как пользовательское событие, можно определить при возникновении события.  
  
 Для автоматической обработки события нажатия для карты событий элемента управления должны быть stock щелкните определенных событий.  
  
##  <a name="a-namefiredblclicka--colecontrolfiredblclick"></a><a name="firedblclick"></a>COleControl::FireDblClick  
 Вызывается инфраструктурой при двойном щелчке мыши по активным элементом управления.  
  
```  
void FireDblClick();
```  
  
### <a name="remarks"></a>Примечания  
 Если оно определено как пользовательское событие, можно определить при возникновении события.  
  
 Для автоматической обработки события Двойное нажатие кнопки, карты событий элемента управления должны быть акций двойное нажатие кнопки события, определенного.  
  
##  <a name="a-namefireerrora--colecontrolfireerror"></a><a name="fireerror"></a>COleControl::FireError  
 Запускает событие ошибки акций.  
  
```  
void FireError(
    SCODE scode,  
    LPCTSTR lpszDescription,  
    UINT nHelpID = 0);
```  
  
### <a name="parameters"></a>Параметры  
 *SCODE*  
 Значение кода состояния для создания отчета. Полный список возможных кодов см. в статье [элементы управления ActiveX: Дополнительные темы](../../mfc/mfc-activex-controls-advanced-topics.md).  
  
 `lpszDescription`  
 Описание сообщение об ошибке.  
  
 `nHelpID`  
 Идентификатор справки сообщение об ошибке.  
  
### <a name="remarks"></a>Примечания  
 Это событие предоставляет способ сигналов, в соответствующие места в коде, что произошла ошибка в элементе управления. В отличие от других стандартных событий, например щелчок или MouseMove ошибка не возникает платформой.  
  
 Чтобы сообщить об ошибке, возникающее во время функция get свойства, функция set свойства или метода автоматизации, вызовите [COleControl::ThrowError](#throwerror).  
  
 Реализация элемента управления OLE Stock ошибка событие использует `SCODE` значение. Если элемент управления использует это событие и предназначен для использования в Visual Basic 4.0, будут возникать ошибки, так как `SCODE` значение не поддерживается в Visual Basic.  
  
 Чтобы устранить эту проблему, вручную измените `SCODE` параметр в элементе управления. ODL-файла в **длинные**. Кроме того, любое пользовательское событие, метод или свойство, использующего `SCODE` параметра также приводит к тому же проблема.  
  
##  <a name="a-namefireeventa--colecontrolfireevent"></a><a name="fireevent"></a>COleControl::FireEvent  
 Запускает событие определяемой пользователем из элемента управления с любым количеством необязательных аргументов.  
  
```  
void AFX_CDECL FireEvent(
    DISPID dispid,  
    BYTE* pbParams,  
 ...);
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации событие.  
  
 `pbParams`  
 Дескриптор для типов параметров событий.  
  
### <a name="remarks"></a>Примечания  
 Обычно эта функция не должен вызываться напрямую. Вместо этого будет вызывать функции обработки событий в разделе сопоставления событий объявление класса элемента управления.  
  
 `pbParams` Аргумент является разделенный пробелами список **VTS_**. Одно или несколько из этих значений, разделенных пробелами (не запятыми), составляют список параметров функции. Ниже приведены возможные значения.  
  
|Символ|Тип параметра|  
|------------|--------------------|  
|**VTS_COLOR**|**OLE_COLOR**|  
|**VTS_FONT**|**IFontDisp\***|  
|**VTS_HANDLE**|`HWND`|  
|**VTS_PICTURE**|**IPictureDisp\***|  
|**VTS_OPTEXCLUSIVE**|**OLE_OPTEXCLUSIVE\***|  
|**VTS_TRISTATE**|**OLE_TRISTATE**|  
|**VTS_XPOS_HIMETRIC**|**OLE_XPOS_HIMETRIC**|  
|**VTS_YPOS_HIMETRIC**|**OLE_YPOS_HIMETRIC**|  
|**VTS_XPOS_PIXELS**|**OLE_XPOS_PIXELS**|  
|**VTS_YPOS_PIXELS**|**OLE_YPOS_PIXELS**|  
|**VTS_XSIZE_PIXELS**|**OLE_XSIZE_PIXELS**|  
|**VTS_YSIZE_PIXELS**|**OLE_XSIZE_PIXELS**|  
|**VTS_XSIZE_HIMETRIC**|**OLE_XSIZE_HIMETRIC**|  
|**VTS_YSIZE_HIMETRIC**|**OLE_XSIZE_HIMETRIC**|  
  
> [!NOTE]
>  Дополнительные variant константы определены для всех типов variant, за исключением класса **VTS_FONT** и **VTS_PICTURE**, обеспечивающие указатель константы данных variant. Эти константы именуются **VTS_P** `constantname` соглашение. Например **VTS_PCOLOR** — это указатель на **VTS_COLOR** константой.  
  
##  <a name="a-namefirekeydowna--colecontrolfirekeydown"></a><a name="firekeydown"></a>COleControl::FireKeyDown  
 Вызывается платформой, при нажатии клавиши во время активного пользовательского интерфейса элемента управления.  
  
```  
void FireKeyDown(
    USHORT* pnChar,  
    short nShiftState);
```  
  
### <a name="parameters"></a>Параметры  
 `pnChar`  
 Указатель на значение виртуальный код клавиши нажатой клавише. Список стандартных кодов виртуального ключа см. в разделе Winuser.h  
  
 `nShiftState`  
 Содержит сочетание следующих флагов.  
  
- **SHIFT_MASK** клавиша SHIFT была нажата в ходе выполнения действия.  
  
- **CTRL_MASK** клавиша CTRL была нажата в ходе выполнения действия.  
  
- **ALT_MASK** клавиша ALT была нажата в ходе выполнения действия.  
  
### <a name="remarks"></a>Примечания  
 Если оно определено как пользовательское событие, можно определить при возникновении события.  
  
 Для автоматической обработки события KeyDown, карты событий элемента управления должны быть акций определенные события KeyDown.  
  
##  <a name="a-namefirekeypressa--colecontrolfirekeypress"></a><a name="firekeypress"></a>COleControl::FireKeyPress  
 Вызывается платформой, когда нажимается и отпускается, пока активно пользовательского интерфейса пользовательского элемента управления внутри контейнера ключа.  
  
```  
void FireKeyPress(USHORT* pnChar);
```  
  
### <a name="parameters"></a>Параметры  
 `pnChar`  
 Указатель на значение символа нажатой клавиши.  
  
### <a name="remarks"></a>Примечания  
 Если оно определено как пользовательское событие, можно определить при возникновении события.  
  
 Получатель события может изменить `pnChar`, например, преобразования всех символов нижнего регистра в верхний регистр. Если вы хотите изучить измененный символ, переопределить `OnKeyPressEvent`.  
  
 Для автоматической обработки события KeyPress, карты событий элемента управления должны быть акций событие KeyPress определен.  
  
##  <a name="a-namefirekeyupa--colecontrolfirekeyup"></a><a name="firekeyup"></a>COleControl::FireKeyUp  
 Вызывается инфраструктурой при отпускании клавиши, если пользовательский элемент управления активен пользовательского интерфейса в контейнере.  
  
```  
void FireKeyUp(
    USHORT* pnChar,  
    short nShiftState);
```  
  
### <a name="parameters"></a>Параметры  
 `pnChar`  
 Указатель на значение виртуальный код клавиши, выпущенные ключа. Список стандартных кодов виртуального ключа см. в разделе Winuser.h  
  
 `nShiftState`  
 Содержит сочетание следующих флагов.  
  
- **SHIFT_MASK** клавиша SHIFT была нажата в ходе выполнения действия.  
  
- **CTRL_MASK** клавиша CTRL была нажата в ходе выполнения действия.  
  
- **ALT_MASK** клавиша ALT была нажата в ходе выполнения действия.  
  
### <a name="remarks"></a>Примечания  
 Если оно определено как пользовательское событие, можно определить при возникновении события.  
  
 Для автоматической обработке событие KeyUp, карты событий элемента управления должны быть акций событие KeyUp определен.  
  
##  <a name="a-namefiremousedowna--colecontrolfiremousedown"></a><a name="firemousedown"></a>COleControl::FireMouseDown  
 Вызывается платформой, при нажатии кнопки мыши над active пользовательского элемента управления.  
  
```  
void FireMouseDown(
    short nButton,  
    short nShiftState,  
    OLE_XPOS_PIXELS x,  
    OLE_YPOS_PIXELS y);
```  
  
### <a name="parameters"></a>Параметры  
 `nButton`  
 Нажата кнопка мыши числовое значение. Он может содержать одно из следующих значений:  
  
- **LEFT_BUTTON** нажатой левую кнопку мыши.  
  
- **MIDDLE_BUTTON** средняя кнопка мыши была нажата кнопка.  
  
- **RIGHT_BUTTON** правая кнопка мыши была нажата кнопка.  
  
 `nShiftState`  
 Содержит сочетание следующих флагов.  
  
- **SHIFT_MASK** клавиша SHIFT была нажата в ходе выполнения действия.  
  
- **CTRL_MASK** клавиша CTRL была нажата в ходе выполнения действия.  
  
- **ALT_MASK** клавиша ALT была нажата в ходе выполнения действия.  
  
 *x*  
 Координата x указателя при нажатой кнопке мыши. Координата указывается относительно левого верхнего угла окна элемента управления.  
  
 *y*  
 Координата по оси y курсора при нажатой кнопке мыши. Координата указывается относительно левого верхнего угла окна элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Если оно определено как пользовательское событие, можно определить при возникновении события.  
  
 Для автоматической обработки события MouseDown, карты событий элемента управления должны быть акций события MouseDown определен.  
  
##  <a name="a-namefiremousemovea--colecontrolfiremousemove"></a><a name="firemousemove"></a>COleControl::FireMouseMove  
 Вызывается инфраструктурой при перемещении курсора над активной пользовательского элемента управления.  
  
```  
void FireMouseMove(
    short nButton,  
    short nShiftState,  
    OLE_XPOS_PIXELS x,  
    OLE_YPOS_PIXELS y);
```  
  
### <a name="parameters"></a>Параметры  
 `nButton`  
 Числовое значение из кнопок мыши нажата. Содержит комбинацию из следующих значений:  
  
- **LEFT_BUTTON** левая кнопка мыши была нажата кнопка в ходе выполнения действия.  
  
- **MIDDLE_BUTTON** средняя кнопка мыши была нажата кнопка в ходе выполнения действия.  
  
- **RIGHT_BUTTON** правая кнопка мыши была нажата кнопка в ходе выполнения действия.  
  
 `nShiftState`  
 Содержит сочетание следующих флагов.  
  
- **SHIFT_MASK** клавиша SHIFT была нажата в ходе выполнения действия.  
  
- **CTRL_MASK** клавиша CTRL была нажата в ходе выполнения действия.  
  
- **ALT_MASK** клавиша ALT была нажата в ходе выполнения действия.  
  
 *x*  
 Координата курсора по оси x. Координата указывается относительно левого верхнего угла окна элемента управления.  
  
 *y*  
 Координата по оси y курсора. Координата указывается относительно левого верхнего угла окна элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Если оно определено как пользовательское событие, можно определить при возникновении события.  
  
 Для автоматической обработки события MouseMove, карты событий элемента управления должны быть акций события MouseMove, определенного.  
  
##  <a name="a-namefiremouseupa--colecontrolfiremouseup"></a><a name="firemouseup"></a>COleControl::FireMouseUp  
 Вызывается инфраструктурой при отпускании кнопки мыши над active пользовательского элемента управления.  
  
```  
void FireMouseUp(
    short nButton,  
    short nShiftState,  
    OLE_XPOS_PIXELS x,  
    OLE_YPOS_PIXELS y);
```  
  
### <a name="parameters"></a>Параметры  
 `nButton`  
 Числовое значение отпущена кнопка мыши. Он может принимать одно из следующих значений:  
  
- **LEFT_BUTTON** был выпущен левую кнопку мыши.  
  
- **MIDDLE_BUTTON** был выпущен средней кнопки мыши.  
  
- **RIGHT_BUTTON** был выпущен правой кнопкой мыши.  
  
 `nShiftState`  
 Содержит сочетание следующих флагов.  
  
- **SHIFT_MASK** клавиша SHIFT была нажата в ходе выполнения действия.  
  
- **CTRL_MASK** клавиша CTRL была нажата в ходе выполнения действия.  
  
- **ALT_MASK** клавиша ALT была нажата в ходе выполнения действия.  
  
 *x*  
 Координата по оси x курсор, когда кнопка мыши отпущена. Координата указывается относительно левого верхнего угла окна элемента управления.  
  
 *y*  
 Координата по оси y курсора, когда кнопка мыши отпущена. Координата указывается относительно левого верхнего угла окна элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Если оно определено как пользовательское событие, можно определить при возникновении события.  
  
 Для автоматической обработки события MouseUp, карты событий элемента управления должны быть акций события MouseUp, определенного.  
  
##  <a name="a-namefirereadystatechangea--colecontrolfirereadystatechange"></a><a name="firereadystatechange"></a>COleControl::FireReadyStateChange  
 Запускает событие, с текущим значением состояние готовности элемента управления.  
  
```  
void FireReadyStateChange();
```  
  
### <a name="remarks"></a>Примечания  
 Состояние «Готово» может принимать одно из следующих значений:  
  
 **READYSTATE_UNINITIALIZED**  
 Состояние инициализации по умолчанию  
  
 **READYSTATE_LOADING**  
 Элемент управления загружает его свойства  
  
 **READYSTATE_LOADED**  
 Элемент управления был инициализирован.  
  
 **READYSTATE_INTERACTIVE**  
 Элемент управления имеет достаточно данных, чтобы быть интерактивным, но не все асинхронные данных еще загружается.  
  
 `READYSTATE_COMPLETE`  
 Элемент управления имеет все данные  
  
 Используйте [GetReadyState](#getreadystate) в определении готовности текущего элемента управления.  
  
 [InternalSetReadyState](#internalsetreadystate) примет значение, указанное в состоянии готовности, а затем вызывает `FireReadyStateChange`.  
  
##  <a name="a-namegetactivationpolicya--colecontrolgetactivationpolicy"></a><a name="getactivationpolicy"></a>COleControl::GetActivationPolicy  
 Изменяет поведение активации по умолчанию элемент управления, поддерживающий `IPointerInactive` интерфейса.  
  
```  
virtual DWORD GetActivationPolicy();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сочетание флагов из **POINTERINACTIVE** перечисления. Ниже перечислены возможные флаги  
  
 **POINTERINACTIVE_ACTIVATEONENTRY**  
 Объект должен быть активирован, когда указатель мыши перемещается на его во время операции перемещения мыши на месте.  
  
 **POINTERINACTIVE_DEACTIVATEONLEAVE**  
 Объект следует деактивировать, когда указатель мыши выходит за границы объекта во время операции перемещения мыши.  
  
 **POINTERINACTIVE_ACTIVATEONDRAG**  
 Объект необходимо активировать при перемещении мыши над ним во время перетаскивания на место и операция перетаскивания.  
  
### <a name="remarks"></a>Примечания  
 При `IPointerInactive` интерфейс включен, будут делегировать контейнер `WM_SETCURSOR` и `WM_MOUSEMOVE` его сообщения. `COleControl`в реализации этого интерфейса отправляет эти сообщения через схему сообщений для элемента управления, после настройки мыши координирует соответствующим образом.  
  
 Каждый раз, когда контейнер получает `WM_SETCURSOR` или `WM_MOUSEMOVE` сообщений с помощью указателя мыши над поддержкой неактивных объектов `IPointerInactive`, он должен вызывать `GetActivationPolicy` на интерфейс и возврата флагов из **POINTERINACTIVE** перечисления.  
  
 Можно обработать эти сообщения как обычный оконных сообщений, добавив соответствующие записи в схеме сообщений. В обработчиков, избегайте использования `m_hWnd` переменной-члена (или любой функции-члены, он использует) без предварительной проверки, что его значение не является **NULL**.  
  
 Любой объект, предназначенный для более чем установить курсор мыши или срабатывание события перемещения мыши, такие как обеспечить специальные визуальную обратную связь, должен возвращать **POINTERINACTIVE_ACTIVATEONENTRY** флаг и нарисуйте отзыв только в том случае, когда активны. Если объект возвращает этот флаг, контейнер следует активировать его на место сразу и пересылать его же сообщение, вызывающее вызов `GetActivationPolicy`.  
  
 Если оба **POINTERINACTIVE_ACTIVATEONENTRY** и **POINTERINACTIVE_DEACTIVATEONLEAVE** флаги возвращаются, то объект будет загружаться только когда указатель мыши находится над объектом. Если только **POINTERINACTIVE_ACTIVATEONENTRY** флаг возвращается, а затем объект активируется только после при первом входе мыши объект.  
  
 Вы также можете неактивный элемент управления быть целевым объектом перетаскивания OLE операции перетаскивания. Это требует активации элемента управления в данный момент пользователь перетаскивает объект, чтобы окна элемента управления, можно зарегистрировать как цель перетаскивания. Чтобы активации возникает во время перетаскивания, вернуть **POINTERINACTIVE_ACTIVATEONDRAG** флаг:  
  
 [!code-cpp[NVC_MFCAxCtl&#1;](../../mfc/reference/codesnippet/cpp/colecontrol-class_1.cpp)]  
  
 Сообщаются сведения путем `GetActivationPolicy` не должны кэшироваться в контейнере. Вместо этого данный метод должен вызываться при каждом входе мыши неактивного объекта.  
  
 Если объект неактивные не запрашивает быть активирована, когда указатель мыши перемещается на его месте, контейнера должен отправлять последующие `WM_SETCURSOR` сообщений для этого объекта путем вызова [OnInactiveSetCursor](#oninactivesetcursor) до тех пор, пока остается указатель мыши над объектом.  
  
 Включение `IPointerInactive` интерфейс обычно означает, что элемент управления может обрабатывать сообщения от мыши в любое время. Чтобы получить это поведение в контейнере, который не поддерживает `IPointerInactive` интерфейс, необходимо будет управлять всегда вызывается при отображении, означает, что элемент управления должен иметь **OLEMISC_ACTIVATEWHENVISIBLE** флага среди прочих флаги. Тем не менее, для предотвращения этого флага из вступают в силу в контейнере, поддерживает `IPointerInactive`, также можно указать **OLEMISC_IGNOREACTIVATEWHENVISIBLE** флаг:  
  
 [!code-cpp[NVC_MFCAxCtl&#10;](../../mfc/reference/codesnippet/cpp/colecontrol-class_2.cpp)]  
  
##  <a name="a-namegetambientpropertya--colecontrolgetambientproperty"></a><a name="getambientproperty"></a>COleControl::GetAmbientProperty  
 Возвращает значение внешнее свойство контейнера.  
  
```  
BOOL GetAmbientProperty(
    DISPID dispid,  
    VARTYPE vtProp,  
    void* pvProp);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispid*  
 Идентификатор диспетчеризации требуемое внешнее свойство.  
  
 `vtProp`  
 Тип variant тег, который указывает тип значения должен быть возвращен в `pvProp`.  
  
 `pvProp`  
 Указатель на адрес переменной, которая будет получать значение свойства или возвращаемое значение. Фактический тип указателя this должен соответствует типу, заданному параметром `vtProp`.  
  
|vtProp|Тип pvProp|  
|------------|--------------------|  
|`VT_BOOL`|**BOOL\***|  
|`VT_BSTR`|**CString\***|  
|`VT_I2`|**короткий\***|  
|`VT_I4`|**длинное\***|  
|`VT_R4`|**число с плавающей запятой\***|  
|`VT_R8`|**Double\***|  
|`VT_CY`|**ПОЛУГОДИЕ\***|  
|**VT_COLOR**|**OLE_COLOR\***|  
|**VT_DISPATCH**|**LPDISPATCH\***|  
|**VT_FONT**|**LPFONTDISP\***|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если поддерживается внешнее свойство; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если вы используете `GetAmbientProperty` для извлечения свойства окружения DisplayName и ScaleUnits установите `vtProp` для `VT_BSTR` и `pvProp` для **CString\***. Если получено свойство Font окружения `vtProp` для **VT_FONT** и `pvProp` для **LPFONTDISP\***.  
  
 Обратите внимание, что функции уже предоставляются для общих свойства окружающей среды, таких как [AmbientBackColor](#ambientbackcolor) и [AmbientFont](#ambientfont).  
  
##  <a name="a-namegetappearancea--colecontrolgetappearance"></a><a name="getappearance"></a>COleControl::GetAppearance  
 Реализует функцию Get стандартных свойств внешнего вида элемента управления.  
  
```  
short GetAppearance ();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение указывает текущую настройку внешнего вида как **короткие** ( `VT_I2`) значение в случае успешного выполнения. Это значение равно нулю, если внешний вид элемента управления является плоский и 1, если внешний вид элемента управления является 3D.  
  
##  <a name="a-namegetbackcolora--colecontrolgetbackcolor"></a><a name="getbackcolor"></a>COleControl::GetBackColor  
 Реализует функцию Get стандартное свойство BackColor элемента управления.  
  
```  
OLE_COLOR GetBackColor();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение указывает текущий цвет фона как **OLE_COLOR** значение в случае успешного выполнения. Это значение может быть переведен в **COLORREF** значение с помощью вызова `TranslateColor`.  
  
##  <a name="a-namegetborderstylea--colecontrolgetborderstyle"></a><a name="getborderstyle"></a>COleControl::GetBorderStyle  
 Реализует функцию Get стандартное свойство BorderStyle элемента управления.  
  
```  
short GetBorderStyle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 1, если элемент управления имеет обычный границы; 0, если элемент управления не имеет рамки.  
  
##  <a name="a-namegetcapturea--colecontrolgetcapture"></a><a name="getcapture"></a>COleControl::GetCapture  
 Определяет, является ли `COleControl` объекта захват мыши.  
  
```  
CWnd* GetCapture();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если активирован и безоконный элемент управления возвращает **это** элемента управления в настоящее время имеет захват мыши (в зависимости от контейнера элемента управления), или **NULL** , если он не поддерживает запись.  
  
 В противном случае — возвращает `CWnd` объект, захвативший мышь (то же, что `CWnd::GetCapture`).  
  
### <a name="remarks"></a>Примечания  
 Активированные безоконный элемент управления получает мыши при записи [SetCapture](#setcapture) вызывается.  
  
##  <a name="a-namegetclassida--colecontrolgetclassid"></a><a name="getclassid"></a>COleControl::GetClassID  
 Вызывается платформой для получения идентификатора класса элемента управления OLE.  
  
```  
virtual HRESULT GetClassID(LPCLSID pclsid) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 *pclsid*  
 Указатель на местоположение кода класса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если вызов не был успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Обычно реализуется [IMPLEMENT_OLECREATE_EX](class-factories-and-licensing.md#implement_olecreate_ex).  
  
##  <a name="a-namegetclientoffseta--colecontrolgetclientoffset"></a><a name="getclientoffset"></a>COleControl::GetClientOffset  
 Возвращает разницу между левом верхнем углу прямоугольной области элемента управления и верхней левой части клиентской области.  
  
```  
virtual void GetClientOffset(long* pdxOffset, long* pdyOffset) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *pdxOffset*  
 Указатель на горизонтальное смещение клиентской области элемента управления OLE.  
  
 *pdyOffset*  
 Указатель на вертикальное смещение клиентской области элемента управления OLE.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления OLE имеет прямоугольную область в пределах своего контейнера. Клиентская область элемента управления — область элемента управления, за исключением границами и полосами прокрутки. Извлекает смещение `GetClientOffset` разница между верхней левой части прямоугольную область элемента управления и верхней левой части клиентской области. Если элемент управления имеет неклиентские элементы, отличные от стандартных границ и полос прокрутки, переопределяют эту функцию-член для указания смещения.  
  
##  <a name="a-namegetclientrecta--colecontrolgetclientrect"></a><a name="getclientrect"></a>COleControl::GetClientRect  
 Возвращает размер клиентской области элемента управления.  
  
```  
virtual void GetClientRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указатель на `RECT` структуру, содержащую измерения клиентской области безоконный элемент управления, то есть размер элемента управления, за вычетом границы окна, кадры, полосы прокрутки и т. д. `lpRect` Параметр указывает размер клиентской области элемента управления, не его положение.  
  
##  <a name="a-namegetclientsitea--colecontrolgetclientsite"></a><a name="getclientsite"></a>COleControl::GetClientSite  
 Запрашивает объект для указателя на текущий сайт клиента в пределах своего контейнера.  
  
```  
LPOLECLIENTSITE GetClientSite();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий сайт клиентского элемента управления в его контейнере.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый указатель ссылается на экземпляр `IOleClientSite`. `IOleClientSite` Интерфейс, реализуемый контейнерами, является представлением объекта контекста: где он прикреплен в документе, где он получает свое хранилище, пользовательский интерфейс и другие ресурсы.  
  
##  <a name="a-namegetcontrolflagsa--colecontrolgetcontrolflags"></a><a name="getcontrolflags"></a>COleControl::GetControlFlags  
 Извлекает параметры управления флаг.  
  
```  
virtual DWORD GetControlFlags();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Оператором OR сочетание флагов из перечисления ControlFlags:  
  
 `enum ControlFlags {`  
  
 `fastBeginPaint = 0x0001,`  
  
 `clipPaintDC = 0x0002,`  
  
 `pointerInactive = 0x0004,`  
  
 `noFlickerActivate = 0x0008,`  
  
 `windowlessActivate = 0x0010,`  
  
 `canOptimizeDraw = 0x0020,`  
  
 `};`  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `GetControlFlags` возвращает `fastBeginPaint | clipPaintDC`.  
  
 `fastBeginPaint`  
 Если задано, функция использует begin paint специально для элементов управления OLE, а не [BeginPaint](http://msdn.microsoft.com/library/windows/desktop/dd183362) API (значение по умолчанию).  
  
 `clipPaintDC`  
 Если не задано, отключает вызов `IntersectClipRect` внесенных `COleControl` и повышает скорость. Если вы используете активации без окна, этот флаг не оказывает влияния.  
  
 `pointerInactive`  
 Если задано, обеспечивает взаимодействие с мышью, пока элемент управления неактивен, позволяя `COleControl`реализация `IPointerInactive` интерфейс, который по умолчанию отключена.  
  
 `noFlickerActivate`  
 Если задано, устраняет дополнительный графических операций и им мерцание. Используется, когда элемент управления рисует себя в одинаково в состояниях неактивными. Если вы используете активации без окна, этот флаг не оказывает влияния.  
  
 `windowlessActivate`  
 Если задано, определяет активации без окна элемента управления.  
  
 `canOptimizeDraw`  
 Если задано, указывает элемент управления выполняет оптимизированного рисунком, если контейнер поддерживает его.  
  
 Дополнительные сведения о `GetControlFlags` и другими оптимизациями элементов управления OLE, в разделе [элементы управления ActiveX: оптимизация](../../mfc/mfc-activex-controls-optimization.md).  
  
##  <a name="a-namegetcontrolsizea--colecontrolgetcontrolsize"></a><a name="getcontrolsize"></a>COleControl::GetControlSize  
 Получает размер окна элемента управления OLE.  
  
```  
void GetControlSize(
    int* pcx,  
    int* pcy);
```  
  
### <a name="parameters"></a>Параметры  
 *PCX*  
 Указывает ширину элемента управления в пикселях.  
  
 *pcy*  
 Задает высоту элемента управления в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что все координаты для управления windows относительно верхнего левого угла элемента управления.  
  
##  <a name="a-namegetdca--colecontrolgetdc"></a><a name="getdc"></a>COleControl::GetDC  
 Обеспечивает безоконный объект контекста устройства get экранов (или совместимые) из контейнера.  
  
```  
CDC* GetDC(
    LPCRECT lprcRect = NULL,
    DWORD dwFlags = OLEDC_PAINTBKGND);
```  
  
### <a name="parameters"></a>Параметры  
 *lprcRect*  
 Указатель на прямоугольник безоконный элемент управления хочет перерисовывает в клиентских координатах элемента управления. **NULL** означает полный объект экстента.  
  
 `dwFlags`  
 Атрибуты рисования контекст устройства. Доступны варианты:  
  
- **OLEDC_NODRAW** показывает, что объект не будет использовать контекст устройства для выполнения любое изображение просто, но для получения сведений об устройстве отображения. Контейнер необходимо просто передать окна контроллера домена без дальнейшей обработки.  
  
- **OLEDC_PAINTBKGND** запросов, что контейнер в качестве фона перед возвратом DC. Объект следует использовать этот флаг, если он запрашивает контроллер домена для перерисовки области с прозрачным фоном.  
  
- **OLEDC_OFFSCREEN** информирует контейнер, который хочет объект визуализации в битовом изображении, который затем должны копироваться на экране. Объект должен использовать этот флаг, при операции рисования, которые он собирается выполнить создает множество мерцание. Контейнер может выполнять этот запрос или нет. Однако если этот флаг не установлен, контейнер должен передать обратно на экране контроллера домена. Это позволяет выполнять операции прямой экран, например отображение выделения объекты (через **XOR** операции).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на контекст устройства отображения для контейнера `CWnd` клиентской области успешно; в противном случае возвращаемое значение при **NULL**. Контекст устройства отображения можно использовать в последующих функций GDI для рисования в клиентской области окна контейнера.  
  
### <a name="remarks"></a>Примечания  
 [ReleaseDC](#releasedc) для освободить контекст после рисования необходимо вызвать функцию-член. При вызове `GetDC`, они хотят привлечь в их собственных клиентских координат прямоугольника передать объекты. `GetDC`преобразует их в координаты клиентской области контейнера. Объект не должен запросить нужный рисования прямоугольник, превышающий собственный клиентский прямоугольник область, размер которой можно получить с помощью [метода GetClientRect](#getclientrect). Это предотвращает случайно рисования, где они не должны объектов.  
  
##  <a name="a-namegetenableda--colecontrolgetenabled"></a><a name="getenabled"></a>COleControl::GetEnabled  
 Реализует функцию Get для хранения свойство Enabled элемента управления.  
  
```  
BOOL GetEnabled();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления включен; в противном случае — 0.  
  
##  <a name="a-namegetextendedcontrola--colecontrolgetextendedcontrol"></a><a name="getextendedcontrol"></a>COleControl::GetExtendedControl  
 Получает указатель на объект, который обслуживается контейнера, представляющий элемент управления с помощью расширенного набора свойств.  
  
```  
LPDISPATCH GetExtendedControl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на контейнере расширенных объект элемента управления. Если отсутствует объект, значение равно **NULL**.  
  
 Этот объект может быть подвергнуты его `IDispatch` интерфейса. Можно также использовать `QueryInterface` для получения других доступных интерфейсов, предоставляемых объектом. Тем не менее объект не требуется для поддержки конкретного набора интерфейсов. Обратите внимание, что полагается на функции, в которых объект контейнера расширенного элемента управления ограничивает переносимость в другие контейнеры произвольный элемент управления.  
  
### <a name="remarks"></a>Примечания  
 Функцию, которая вызывает эту функцию несет ответственность за освобождение указатель после завершения работы с объектом. Обратите внимание, что контейнер не требуется для поддержки этого объекта.  
  
##  <a name="a-namegetfocusa--colecontrolgetfocus"></a><a name="getfocus"></a>COleControl::GetFocus  
 Определяет, является ли `COleControl` объект имеет фокус.  
  
```  
CWnd* GetFocus();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если активирован и безоконный элемент управления возвращает **это** элемента управления в данный момент имеет фокус ввода (в зависимости от контейнера элемента управления), или **NULL** , если он не имеет фокус.  
  
 В противном случае — возвращает `CWnd` объекта, имеющего фокус (то же, что `CWnd::GetFocus`).  
  
### <a name="remarks"></a>Примечания  
 Активированные безоконный элемент управления получает фокус при [SetFocus](#setfocus) вызывается.  
  
##  <a name="a-namegetfonta--colecontrolgetfont"></a><a name="getfont"></a>COleControl::GetFont  
 Реализует свойство Font функции Get.  
  
```  
LPFONTDISP GetFont();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс диспетчеризации шрифта элемента управления для хранения свойств шрифта.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что вызывающий объект должен освободить объект после завершения. В реализации элемента управления, используйте `InternalGetFont` для доступа к объекту акций шрифта элемента управления. Дополнительные сведения по использованию шрифтов в элементе управления, см. в статье [элементы управления ActiveX: использование шрифтов в элементе управления ActiveX](../../mfc/mfc-activex-controls-using-fonts.md).  
  
##  <a name="a-namegetfonttextmetricsa--colecontrolgetfonttextmetrics"></a><a name="getfonttextmetrics"></a>COleControl::GetFontTextMetrics  
 Измеряет показатели текст для любого `CFontHolder` объектов, принадлежащих данному элементу управления.  
  
```  
void GetFontTextMetrics(
    LPTEXTMETRIC lptm,  
    CFontHolder& fontHolder);
```  
  
### <a name="parameters"></a>Параметры  
 `lptm`  
 Указатель на [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) структуры.  
  
 `fontHolder`  
 Ссылка на [CFontHolder](../../mfc/reference/cfontholder-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Такого шрифта, которые могут быть выбраны с [COleControl::SelectFontObject](#selectfontobject) функции. `GetFontTextMetrics`Инициализирует `TEXTMETRIC` структуры, на который указывает `lptm` с допустимым метрики сведения о `fontHolder`, шрифт, в случае успешного выполнения или заполнять структуры нулями, если завершилась неудачно. Следует использовать эту функцию вместо [GetTextMetrics](http://msdn.microsoft.com/library/windows/desktop/dd144941) при рисование элемента управления, возможно, элементы управления, как и любой внедренные объекты OLE, необходимые для визуализации сами в метафайл.  
  
 `TEXTMETRIC` Структуры для шрифта по умолчанию используется при обновлении [SelectFontObject](#selectfontobject) вызывается функция. Следует вызвать `GetFontTextMetrics` только после того, выбрав свойство Font для обеспечения сведениями является допустимым.  
  
##  <a name="a-namegetforecolora--colecontrolgetforecolor"></a><a name="getforecolor"></a>COleControl::GetForeColor  
 Реализует функцию Get свойство цвет переднего плана.  
  
```  
OLE_COLOR GetForeColor();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение указывает, как текущий цвет **OLE_COLOR** значение в случае успешного выполнения. Это значение может быть переведен в [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение с помощью вызова `TranslateColor`.  
  
##  <a name="a-namegethwnda--colecontrolgethwnd"></a><a name="gethwnd"></a>COleControl::GetHwnd  
 Реализует функцию Get свойства акций hWnd.  
  
```  
OLE_HANDLE GetHwnd();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор окна элемента управления OLE, при его наличии; в противном случае **NULL**.  
  
##  <a name="a-namegetmessagestringa--colecontrolgetmessagestring"></a><a name="getmessagestring"></a>COleControl::GetMessageString  
 Вызывается платформой для получения короткую строку, описывающую назначение элемента меню, который определяется `nID`.  
  
```  
virtual void GetMessageString(
    UINT nID,  
    CString& rMessage) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента меню.  
  
 `rMessage`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта, через который возвращается строка.  
  
### <a name="remarks"></a>Примечания  
 Это может использоваться для получения сообщений для отображения в строке состояния, снимая элемент меню. Реализация по умолчанию пытается загрузить строку ресурса, определяемого `nID`.  
  
##  <a name="a-namegetnotsupporteda--colecontrolgetnotsupported"></a><a name="getnotsupported"></a>COleControl::GetNotSupported  
 Запрещает доступ к значению свойства элемента управления для пользователя.  
  
```  
void GetNotSupported();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции вместо функции Get любого свойства, где получение свойства пользователем элемента управления не поддерживается. Примером может служить свойство, которое доступно только для записи.  
  
##  <a name="a-namegetreadystatea--colecontrolgetreadystate"></a><a name="getreadystate"></a>COleControl::GetReadyState  
 Возвращает состояние готовности элемента управления.  
  
```  
long GetReadyState();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние готовности элемента управления, одно из следующих значений:  
  
 **READYSTATE_UNINITIALIZED**  
 Состояние инициализации по умолчанию  
  
 **READYSTATE_LOADING**  
 Элемент управления загружает его свойства  
  
 **READYSTATE_LOADED**  
 Элемент управления был инициализирован.  
  
 **READYSTATE_INTERACTIVE**  
 Элемент управления имеет достаточно данных, чтобы быть интерактивным, но не все асинхронные данных еще загружается.  
  
 `READYSTATE_COMPLETE`  
 Элемент управления имеет все данные  
  
### <a name="remarks"></a>Примечания  
 Большинство простых элементов управления не требуется различать **LOADED** и `INTERACTIVE`. Тем не менее элементы управления, поддерживающие свойства пути данных не можно быть интерактивным, пока по крайней мере некоторых данных принимается асинхронно. Элемент управления должен попытаться стать интерактивных как можно быстрее.  
  
##  <a name="a-namegetrectincontainera--colecontrolgetrectincontainer"></a><a name="getrectincontainer"></a>COleControl::GetRectInContainer  
 Получает координаты прямоугольника элемента управления относительно контейнера, выраженный в единицах измерения устройства.  
  
```  
BOOL GetRectInContainer(LPRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указатель на структуру прямоугольник, в который будут копироваться координаты элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления является активным на месте; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Прямоугольник действителен только в том случае, если элемент управления является активным на месте.  
  
##  <a name="a-namegetstocktextmetricsa--colecontrolgetstocktextmetrics"></a><a name="getstocktextmetrics"></a>COleControl::GetStockTextMetrics  
 Измеряет показатели текст акций шрифта свойства элемента управления, которую можно выбрать с помощью [SelectStockFont](#selectstockfont) функции.  
  
```  
void GetStockTextMetrics(LPTEXTMETRIC lptm);
```  
  
### <a name="parameters"></a>Параметры  
 `lptm`  
 Указатель на [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) структуры.  
  
### <a name="remarks"></a>Примечания  
 `GetStockTextMetrics` Функция будет инициализировать `TEXTMETRIC` структуры, на который указывает `lptm` с допустимым метрики информации в случае успешного выполнения или заполнения структуры нулями, если завершилась неудачно. Используйте эту функцию, а не [GetTextMetrics](http://msdn.microsoft.com/library/windows/desktop/dd144941) при рисование элемента управления, возможно, элементы управления, как и любой внедренные объекты OLE, необходимые для визуализации сами в метафайл.  
  
 `TEXTMETRIC` Структуры для шрифта по умолчанию используется при обновлении `SelectStockFont` вызывается функция. Эту функцию следует вызывать только после выбора акций шрифта для сведений, которые он предоставляет гарантии является допустимым.  
  
##  <a name="a-namegettexta--colecontrolgettext"></a><a name="gettext"></a>COleControl::GetText  
 Реализует функцию Get стандартное свойство Text или Caption.  
  
```  
BSTR GetText();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение элемента управления текстовую строку или строки нулевой длины, если строка не присутствует.  
  
> [!NOTE]
>  Дополнительные сведения о `BSTR` тип данных, в разделе [типы данных](../../mfc/reference/data-types-mfc.md) в разделе макросы и глобальные переменные.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что код, вызывающий эту функцию необходимо вызвать `SysFreeString` строки возвращаются в порядке бесплатно ресурса. В реализации элемента управления, используйте `InternalGetText` для доступа к свойству Text или Caption акций элемента управления.  
  
##  <a name="a-namegetwindowlessdroptargeta--colecontrolgetwindowlessdroptarget"></a><a name="getwindowlessdroptarget"></a>COleControl::GetWindowlessDropTarget  
 Переопределение `GetWindowlessDropTarget` при необходимости безоконный элемент управления для целевой OLE операции перетаскивания.  
  
```  
virtual IDropTarget* GetWindowlessDropTarget();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект `IDropTarget` интерфейса. Так как он не имеет окна, не удалось зарегистрировать объект без окон `IDropTarget` интерфейса. Тем не менее, чтобы участвовать в операции перетаскивания, объект без окон можно по-прежнему реализовывать интерфейс и вернуть его в `GetWindowlessDropTarget`.  
  
### <a name="remarks"></a>Примечания  
 Как правило это потребует, регистрируемого в качестве цели перетаскивания окна элемента управления. Но так как элемент управления не имеет окна свои собственные, контейнер будет использовать отдельное окно местом назначения. Элемент управления просто необходимо предоставить реализацию `IDropTarget` интерфейс, к которому контейнера можно делегировать вызовы в нужное время. Пример:  
  
 [!code-cpp[NVC_MFCAxCtl&#2;](../../mfc/reference/codesnippet/cpp/colecontrol-class_3.cpp)]  
  
##  <a name="a-nameinitializeiidsa--colecontrolinitializeiids"></a><a name="initializeiids"></a>COleControl::InitializeIIDs  
 Информирует о базовом классе IID, элемент управления будет использовать.  
  
```  
void InitializeIIDs(
    const IID* piidPrimary,
    const IID* piidEvents);
```  
  
### <a name="parameters"></a>Параметры  
 *piidPrimary*  
 Указатель на интерфейс идентификатор интерфейса диспетчеризации основного элемента управления.  
  
 *piidEvents*  
 Указатель на интерфейс идентификатор интерфейса событий элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается в конструктор элемента управления для информирования базового класса элемента управления будет использовать идентификаторы интерфейсов.  
  
##  <a name="a-nameinternalgetfonta--colecontrolinternalgetfont"></a><a name="internalgetfont"></a>COleControl::InternalGetFont  
 Обращается к свойство Font элемента управления  
  
```  
CFontHolder& InternalGetFont();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на [CFontHolder](../../mfc/reference/cfontholder-class.md) объект, содержащий акций объект шрифта.  
  
##  <a name="a-nameinternalgettexta--colecontrolinternalgettext"></a><a name="internalgettext"></a>COleControl::InternalGetText  
 Обращается к текст или заголовок, свойство элемента управления.  
  
```  
const CString& InternalGetText();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на строку текста элемента управления.  
  
##  <a name="a-nameinternalsetreadystatea--colecontrolinternalsetreadystate"></a><a name="internalsetreadystate"></a>COleControl::InternalSetReadyState  
 Задает состояние готовности элемента управления.  
  
```  
void InternalSetReadyState(long lNewReadyState);
```  
  
### <a name="parameters"></a>Параметры  
 *lNewReadyState*  
 Состояние готовности, чтобы задать для элемента управления, одно из следующих значений:  
  
 **READYSTATE_UNINITIALIZED**  
 Состояние инициализации по умолчанию  
  
 **READYSTATE_LOADING**  
 Элемент управления загружает его свойства  
  
 **READYSTATE_LOADED**  
 Элемент управления был инициализирован.  
  
 **READYSTATE_INTERACTIVE**  
 Элемент управления имеет достаточно данных, чтобы быть интерактивным, но не все асинхронные данных еще загружается.  
  
 `READYSTATE_COMPLETE`  
 Элемент управления имеет все данные  
  
### <a name="remarks"></a>Примечания  
 Большинство простых элементов управления не требуется различать **LOADED** и `INTERACTIVE`. Тем не менее элементы управления, поддерживающие свойства пути данных не можно быть интерактивным, пока по крайней мере некоторых данных принимается асинхронно. Элемент управления должен попытаться стать интерактивных как можно быстрее.  
  
##  <a name="a-nameinvalidatecontrola--colecontrolinvalidatecontrol"></a><a name="invalidatecontrol"></a>COleControl::InvalidateControl  
 Заставляет элемент управления перерисовка.  
  
```  
void InvalidateControl(
    LPCRECT lpRect = NULL,  
    BOOL bErase = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указатель на область элемента управления необходимо сделать недействительным.  
  
 `bErase`  
 Указывает, является ли фон в пределах области обновления утрачиваются при обработке область обновления.  
  
### <a name="remarks"></a>Примечания  
 Если `lpRect` имеет **NULL** значение, весь элемент управления перерисовывается. Если `lpRect` не **NULL**, это указывает на часть элемента управления прямоугольник, который необходимо сделать недействительным. В случаях, когда элемент управления не имеет окна или в настоящее время не активен, прямоугольник учитывается, и вызов узла клиента [IAdviseSink::OnViewChange](http://msdn.microsoft.com/library/windows/desktop/ms694337) функции-члена. Используйте эту функцию, а не `CWnd::InvalidateRect` или `InvalidateRect`.  
  
##  <a name="a-nameinvalidatergna--colecontrolinvalidatergn"></a><a name="invalidatergn"></a>COleControl::InvalidateRgn  
 Делает недействительным окно контейнера клиентской области в пределах данной области.  
  
```  
void InvalidateRgn(CRgn* pRgn, BOOL bErase = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pRgn`  
 Указатель на [CRgn](../../mfc/reference/crgn-class.md) , определяющий область отображения объекта OLE в недействительное состояние, в клиентских координатах окна. Если этот параметр равен **NULL**, область является весь объект.  
  
 `bErase`  
 Указывает, является ли фон в пределах области недействительным для удаления. Если **TRUE**, удаляются в фоновом режиме. Если **FALSE**, фон не изменяется.  
  
### <a name="remarks"></a>Примечания  
 Это можно использовать для повторной отрисовки без окон элементов управления внутри контейнера. Недопустимая область, а также других областей в область обновления помечен для рисования при следующем [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) отправляется сообщение.  
  
 Если `bErase` — **TRUE** в любой части области обновления фона всей области не только в данной части удаляются.  
  
##  <a name="a-nameisconvertingvbxa--colecontrolisconvertingvbx"></a><a name="isconvertingvbx"></a>COleControl::IsConvertingVBX  
 Разрешает специализированные загрузку элемента управления OLE.  
  
```  
BOOL IsConvertingVBX();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления преобразуется; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 При преобразовании формы, который использует VBX элементов управления, которое использует элементы управления OLE, может потребоваться специальные загрузки кода для элементов управления OLE. Например, при загрузке экземпляра элемента управления OLE, может потребоваться вызов [PX_Font](persistence-of-ole-controls.md#px_font) в ваш `DoPropExchange`:  
  
 [!code-cpp[NVC_MFCAxCtl&#3;](../../mfc/reference/codesnippet/cpp/colecontrol-class_4.cpp)]  
  
 Тем не менее элементы управления VBX не содержал объект шрифта; Каждое свойство font был сохранен по отдельности. В этом случае используется `IsConvertingVBX` для различения этих двух случаях:  
  
 [!code-cpp[NVC_MFCAxCtl&#4;](../../mfc/reference/codesnippet/cpp/colecontrol-class_5.cpp)]  
  
 Другой случай будет, если элемент управления VBX сохранены собственные двоичные данные (в его **VBM_SAVEPROPERTY** обработчик сообщений), и элемент управления OLE сохраняет его двоичные данные в другом формате. Если требуется, чтобы элемент управления OLE обратную совместимость с элементом управления VBX, можно прочитать обе старые и новые форматы, используя `IsConvertingVBX` функции, обращая внимание на ли загрузке VBX элемент управления или элемент управления OLE.  
  
 В элементе управления `DoPropExchange` функции, чтобы проверяет это условие и значение true, если выполнить нагрузки код, предназначенный для этого преобразования (например, в предыдущих примерах). Если элемент управления не преобразуется, чтобы выполнить код нормальной нагрузке. Эта возможность применяется только к элементам управления, выполняется преобразование из VBX аналоги.  
  
##  <a name="a-nameisinvokealloweda--colecontrolisinvokeallowed"></a><a name="isinvokeallowed"></a>COleControl::IsInvokeAllowed  
 Включает вызов метода автоматизации.  
  
```  
BOOL IsInvokeAllowed(DISPID dispid);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления был инициализирован; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Платформа framework реализация **IDispatch::Invoke** вызовов **IsInvokeAllowed** для определения данной функции (идентифицируются `dispid`), могут быть вызваны. Поведение по умолчанию для элемента управления OLE разрешено способов автоматизации вызывается только в том случае, если элемент управления был инициализирован; Тем не менее **IsInvokeAllowed** является виртуальной функцией и может быть заменено при необходимости (если элемент управления используется как сервер автоматизации). Дополнительные сведения см. в статье базы знаний Q166472, «Практическое руководство: использование элемента управления OLE как сервера автоматизации.» Статьи базы знаний, доступны в документации по Visual Studio библиотеки MSDN или в [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="a-nameismodifieda--colecontrolismodified"></a><a name="ismodified"></a>COleControl::IsModified  
 Определяет, был ли изменен состояние элемента управления.  
  
```  
BOOL IsModified();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если состояние элемента управления был изменен с момента последнего сохранения; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Состояние элемента управления изменяется при изменении значения свойства.  
  
##  <a name="a-nameisoptimizeddrawa--colecontrolisoptimizeddraw"></a><a name="isoptimizeddraw"></a>COleControl::IsOptimizedDraw  
 Определяет, поддерживает ли контейнер оптимизированного рисования для текущей операции рисования.  
  
```  
BOOL IsOptimizedDraw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если контейнер поддерживает оптимизированного рисования для текущей операции рисования; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Если поддерживаются оптимизированные рисования элемента управления требуется не выберите старые объекты (перья, кисти, шрифты, т. д.) в контекст устройства после завершения рисования.  
  
##  <a name="a-nameissubclassedcontrola--colecontrolissubclassedcontrol"></a><a name="issubclassedcontrol"></a>COleControl::IsSubclassedControl  
 Вызывается платформой для определения, если управление подклассов элементов управления Windows.  
  
```  
virtual BOOL IsSubclassedControl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления является подклассом; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Необходимо переопределить эту функцию и вернуть **TRUE** Если ваш OLE управления подклассов элемент управления Windows.  
  
##  <a name="a-nameloada--colecontrolload"></a><a name="load"></a>COleControl::Load  
 Сбрасывает все предыдущие данные загружены асинхронно и инициирует новый загрузку асинхронного свойства элемента управления.  
  
```  
void Load(LPCTSTR strNewPath, CDataPathProperty& prop);
```  
  
### <a name="parameters"></a>Параметры  
 *strNewPath*  
 Указатель на строку, содержащую путь, который ссылается на абсолютное расположение свойство асинхронной элемента управления.  
  
 *prop*  
 Объект [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) объекта, реализующего свойства управления асинхронной.  
  
##  <a name="a-namelockinplaceactivea--colecontrollockinplaceactive"></a><a name="lockinplaceactive"></a>COleControl::LockInPlaceActive  
 Запрещает деактивации управления контейнера.  
  
```  
BOOL LockInPlaceActive(BOOL bLock);
```  
  
### <a name="parameters"></a>Параметры  
 `bLock`  
 **Значение TRUE,** при активном состоянии на месте элемента управления будет заблокирован; **FALSE** Если это должен быть разблокирован.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если блокировка была успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что каждый блокировки элемента управления должны сочетаться с разблокирование элемента управления после завершения. Необходимо только заблокировать элемент управления в течение короткого как при обработке события.  
  
##  <a name="a-nameonambientpropertychangea--colecontrolonambientpropertychange"></a><a name="onambientpropertychange"></a>COleControl::OnAmbientPropertyChange  
 Вызывается платформой, при изменении значения внешнее свойство контейнера.  
  
```  
virtual void OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="parameters"></a>Параметры  
 *Идентификатор dispID*  
 Идентификатор отправки измененного, свойства окружения или **DISPID_UNKNOWN** при изменении нескольких свойств.  
  
##  <a name="a-nameonappearancechangeda--colecontrolonappearancechanged"></a><a name="onappearancechanged"></a>COleControl::OnAppearanceChanged  
 Вызывается инфраструктурой при изменении стандартных значение свойства внешнего вида.  
  
```  
virtual void OnAppearanceChanged ();
```  
  
### <a name="remarks"></a>Примечания  
 Если уведомление после изменения этого свойства требуется переопределите эту функцию. Реализация по умолчанию вызывает `InvalidateControl`.  
  
##  <a name="a-nameonbackcolorchangeda--colecontrolonbackcolorchanged"></a><a name="onbackcolorchanged"></a>COleControl::OnBackColorChanged  
 Вызывается платформой, когда изменилось значение свойства BackColor акций.  
  
```  
virtual void OnBackColorChanged();
```  
  
### <a name="remarks"></a>Примечания  
 Если уведомление после изменения этого свойства требуется переопределите эту функцию. Реализация по умолчанию вызывает `InvalidateControl`.  
  
##  <a name="a-nameonborderstylechangeda--colecontrolonborderstylechanged"></a><a name="onborderstylechanged"></a>COleControl::OnBorderStyleChanged  
 Вызывается платформой, когда изменилось значение свойства BorderStyle акций.  
  
```  
virtual void OnBorderStyleChanged();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает `InvalidateControl`.  
  
 Если уведомление после изменения этого свойства требуется переопределите эту функцию.  
  
##  <a name="a-nameonclicka--colecontrolonclick"></a><a name="onclick"></a>COleControl::OnClick  
 Вызывается платформой, когда была нажата кнопка мыши или вызывается stock метод DoClick был вызван.  
  
```  
virtual void OnClick(USHORT iButton);
```  
  
### <a name="parameters"></a>Параметры  
 *iButton*  
 Индекс кнопки мыши. Может принимать одно из следующих значений:  
  
- **LEFT_BUTTON** была нажата левая кнопка мыши.  
  
- **MIDDLE_BUTTON** средняя кнопка мыши была нажата.  
  
- **RIGHT_BUTTON** правая кнопка мыши была нажата.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает `COleControl::FireClick`.  
  
 Переопределение для изменения или расширения обработки по умолчанию эта функция-член.  
  
##  <a name="a-nameonclosea--colecontrolonclose"></a><a name="onclose"></a>COleControl::OnClose  
 Вызывается платформой, когда контейнер элемента управления называется **IOleControl::Close** функции.  
  
```  
virtual void OnClose(DWORD dwSaveOption);
```  
  
### <a name="parameters"></a>Параметры  
 `dwSaveOption`  
 Флаг, указывающий, должен быть сохранен объект перед загрузкой. Допустимые значения:  
  
- `OLECLOSE_SAVEIFDIRTY`  
  
- `OLECLOSE_NOSAVE`  
  
- `OLECLOSE_PROMPTSAVE`  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `OnClose` сохраняет объект элемента управления, если он был изменен и `dwSaveOption` либо `OLECLOSE_SAVEIFDIRTY` или `OLECLOSE_PROMPTSAVE`.  
  
##  <a name="a-nameondoverba--colecontrolondoverb"></a><a name="ondoverb"></a>COleControl::OnDoVerb  
 Вызывается инфраструктурой при вызове контейнером **функция IOleObject::DoVerb** функции-члена.  
  
```  
virtual BOOL OnDoVerb(
    LONG iVerb,  
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `iVerb`  
 Индекс команды управления должен быть вызван.  
  
 `lpMsg`  
 Указатель на сообщение Windows, вызвавшее команду, которую необходимо вызвать.  
  
 `hWndParent`  
 Дескриптор родительского окна элемента управления. Если выполнение команды создает окна (или windows), `hWndParent` следует использовать в качестве родительского.  
  
 `lpRect`  
 Указатель на структуру RECT координаты элемента управления относительно контейнера, в который будут скопированы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если вызов был успешным; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию использует `ON_OLEVERB` и `ON_STDOLEVERB` сообщений записи карты, чтобы определить правильный для вызова функции.  
  
 Переопределите эту функцию, чтобы изменить обработку по умолчанию команды.  
  
##  <a name="a-nameondrawa--colecontrolondraw"></a><a name="ondraw"></a>COleControl::OnDraw  
 Вызывается платформой для рисования элемента управления OLE в ограничивающем прямоугольнике указанного с помощью заданного контекста устройств.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rcBounds,  
    const CRect& rcInvalid);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Контекст устройства, в котором происходит рисование.  
  
 `rcBounds`  
 Прямоугольная область элемента управления, включая границы.  
  
 `rcInvalid`  
 Прямоугольная область элемента управления, который является недопустимым.  
  
### <a name="remarks"></a>Примечания  
 `OnDraw`для просмотра на экране, передача контекста устройства экрана как обычно называется `pDC`. `rcBounds` Параметр указывает прямоугольник в контексте целевого устройства (относительно своего текущего режима сопоставления). `rcInvalid` Параметр является фактический прямоугольник, который является недопустимым. В некоторых случаях это будет область меньшего размера, чем `rcBounds`.  
  
##  <a name="a-nameondrawmetafilea--colecontrolondrawmetafile"></a><a name="ondrawmetafile"></a>COleControl::OnDrawMetafile  
 Вызывается платформой для рисования элемента управления OLE в указанном метафайле контекста устройства с помощью указанного ограничивающем прямоугольнике.  
  
```  
virtual void OnDrawMetafile(
    CDC* pDC,  
    const CRect& rcBounds);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Контекст устройства, в котором происходит рисование.  
  
 `rcBounds`  
 Прямоугольная область элемента управления, включая границы.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает [OnDraw](#ondraw) функции.  
  
##  <a name="a-nameonedita--colecontrolonedit"></a><a name="onedit"></a>COleControl::OnEdit  
 Элемент управления активироваться через UI.  
  
```  
virtual BOOL OnEdit(
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMsg`  
 Указатель на сообщение Windows, которое вызвало команду.  
  
 `hWndParent`  
 Дескриптор родительского окна элемента управления.  
  
 `lpRect`  
 Указатель на прямоугольник, используемые элементом управления в контейнере.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если вызов будет выполнен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это имеет тот же эффект, что и вызов элемента управления `OLEIVERB_UIACTIVATE` команд.  
  
 Эта функция обычно используется как функция-обработчик `ON_OLEVERB` сообщений запись сопоставления. Это делает доступным с командой «Изменить» в меню «Объект» элемента управления. Пример:  
  
 [!code-cpp[NVC_MFCAxCtl&#5;](../../mfc/reference/codesnippet/cpp/colecontrol-class_6.cpp)]  
  
##  <a name="a-nameonenabledchangeda--colecontrolonenabledchanged"></a><a name="onenabledchanged"></a>COleControl::OnEnabledChanged  
 Вызывается платформой, когда изменилось значение свойства Enabled акции.  
  
```  
virtual void OnEnabledChanged();
```  
  
### <a name="remarks"></a>Примечания  
 Если уведомление после изменения этого свойства требуется переопределите эту функцию. Реализация по умолчанию вызывает [InvalidateControl](#invalidatecontrol).  
  
##  <a name="a-nameonenumverbsa--colecontrolonenumverbs"></a><a name="onenumverbs"></a>COleControl::OnEnumVerbs  
 Вызывается инфраструктурой при вызове контейнером **IOleObject::EnumVerbs** функции-члена.  
  
```  
virtual BOOL OnEnumVerbs(LPENUMOLEVERB* ppenumOleVerb);
```  
  
### <a name="parameters"></a>Параметры  
 `ppenumOleVerb`  
 Указатель на **IEnumOLEVERB** объекта, который перечисляет команды элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если доступны команды; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию перечисляет `ON_OLEVERB` записи в схеме сообщений.  
  
 Переопределите эту функцию, чтобы изменить способ перечисление команд по умолчанию.  
  
##  <a name="a-nameoneventadvisea--colecontroloneventadvise"></a><a name="oneventadvise"></a>COleControl::OnEventAdvise  
 Вызывается инфраструктурой при отключении от элемента управления OLE или подключения обработчика событий.  
  
```  
virtual void OnEventAdvise(BOOL bAdvise);
```  
  
### <a name="parameters"></a>Параметры  
 `bAdvise`  
 **Значение TRUE,** указывает, что обработчик событий с момента подключения к элементу управления. **FALSE** указывает, что обработчик событий был отключен от элемента управления.  
  
##  <a name="a-nameonfontchangeda--colecontrolonfontchanged"></a><a name="onfontchanged"></a>COleControl::OnFontChanged  
 Вызывается платформой, при изменении значения свойства шрифта акций.  
  
```  
virtual void OnFontChanged();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает `COleControl::InvalidateControl`. Если элемент управления является создание подкласса элемента управления Windows, реализация по умолчанию также отправляет **WM_SETFONT** сообщение в окно элемента управления.  
  
 Если уведомление после изменения этого свойства требуется переопределите эту функцию.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAxCtl №&6;](../../mfc/reference/codesnippet/cpp/colecontrol-class_7.cpp)]  
  
##  <a name="a-nameonforecolorchangeda--colecontrolonforecolorchanged"></a><a name="onforecolorchanged"></a>COleControl::OnForeColorChanged  
 Вызывается платформой, когда изменилось значение свойства ForeColor акций.  
  
```  
virtual void OnForeColorChanged();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает `InvalidateControl`.  
  
 Если уведомление после изменения этого свойства требуется переопределите эту функцию.  
  
##  <a name="a-nameonfreezeeventsa--colecontrolonfreezeevents"></a><a name="onfreezeevents"></a>COleControl::OnFreezeEvents  
 Вызывается платформой после того как контейнер вызывает **IOleControl::FreezeEvents**.  
  
```  
virtual void OnFreezeEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>Параметры  
 `bFreeze`  
 **Значение TRUE,** Если элемент управления обработка событий зафиксированной; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не выполняет никаких действий.  
  
 Переопределите эту функцию, если требуется дополнительное поведение, когда обработка событий зафиксировать или снять состояние фиксации.  
  
##  <a name="a-nameongetcolorseta--colecontrolongetcolorset"></a><a name="ongetcolorset"></a>COleControl::OnGetColorSet  
 Вызывается инфраструктурой при вызове контейнером **IViewObject::GetColorSet** функции-члена.  
  
```  
virtual BOOL OnGetColorSet(
    DVTARGETDEVICE* ptd,  
    HDC hicTargetDev,  
    LPLOGPALETTE* ppColorSet);
```  
  
### <a name="parameters"></a>Параметры  
 `ptd`  
 Указывает целевое устройство, для которого должны отображаться изображение. Если это значение равно **NULL**, изображения, которые должны отображаться для целевого устройства по умолчанию, обычно устройство отображения.  
  
 `hicTargetDev`  
 Указывает контекст сведения на целевом устройстве, обозначенными `ptd`. Этот параметр может быть контекста устройства, но не обязательно. If `ptd` is **NULL**, `hicTargetDev` should also be **NULL**.  
  
 *ppColorSet*  
 Указатель на расположение, куда следует скопировать набор цветов, которые будут использоваться. Если функция не возвращает набор цветов, **NULL** возвращается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если возвращается набор допустимых цветовых; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Контейнер вызывает данную функцию, чтобы получить все цвета, необходимые для рисования элемента управления OLE. Контейнер можно использовать наборы цвет, полученный вместе с его необходимо указать общую цветовую палитру цветов. Реализация по умолчанию возвращает **FALSE**.  
  
 Переопределите эту функцию для выполнения специальной обработки этого запроса.  
  
##  <a name="a-nameongetcontrolinfoa--colecontrolongetcontrolinfo"></a><a name="ongetcontrolinfo"></a>COleControl::OnGetControlInfo  
 Вызывается платформой, когда контейнер элемента управления запросил сведения об элементе управления.  
  
```  
virtual void OnGetControlInfo(LPCONTROLINFO pControlInfo);
```  
  
### <a name="parameters"></a>Параметры  
 `pControlInfo`  
 Указатель на [CONTROLINFO](http://msdn.microsoft.com/library/windows/desktop/ms680734) структуру, чтобы заполнить.  
  
### <a name="remarks"></a>Примечания  
 Эта информация состоит в описание назначенные клавиши элемента управления. Заполняет реализацию по умолчанию `pControlInfo` с информацией по умолчанию.  
  
 Переопределите эту функцию, если элемент управления должен обрабатывать назначенные клавиши.  
  
##  <a name="a-nameongetdisplaystringa--colecontrolongetdisplaystring"></a><a name="ongetdisplaystring"></a>COleControl::OnGetDisplayString  
 Вызывается средой, чтобы получить строку, представляющую текущее значение свойства, идентифицируемого по `dispid`.  
  
```  
virtual BOOL OnGetDisplayString(
    DISPID dispid,  
    CString& strValue);
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчера свойства элемента управления.  
  
 `strValue`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта, через который возвращается строка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если строка была возвращена в *strValue;* 0 в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если элемент управления имеет свойства, значение которого не может напрямую преобразуется в строку и необходимо, чтобы значение свойства для отображения в обозревателе свойств предоставленного контейнера.  
  
##  <a name="a-nameongetinplacemenua--colecontrolongetinplacemenu"></a><a name="ongetinplacemenu"></a>COleControl::OnGetInPlaceMenu  
 Вызывается инфраструктурой при активации для получения меню, чтобы объединить в существующее меню контейнера пользовательского интерфейса элемента управления.  
  
```  
virtual HMENU OnGetInPlaceMenu();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор меню элемента управления или **NULL** Если элемент управления не имеет ни одного. Реализация по умолчанию возвращает **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о слиянии OLE ресурсы см. в статье [меню и ресурсы (OLE)](../../mfc/menus-and-resources-ole.md).  
  
##  <a name="a-nameongetnaturalextenta--colecontrolongetnaturalextent"></a><a name="ongetnaturalextent"></a>COleControl::OnGetNaturalExtent  
 Вызывается средой в ответ на контейнер **IViewObjectEx::GetNaturalExtent** запроса.  
  
```  
virtual BOOL OnGetNaturalExtent(
    DWORD dwAspect,
    LONG lindex,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```  
  
### <a name="parameters"></a>Параметры  
 `dwAspect`  
 Указывает способ представления объекта. Представления включают содержимое, значок, эскиз или печати документа. Допустимые значения берутся из перечисления [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) или **DVASPECT2**.  
  
 *Индекс*  
 Часть объекта, который представляет интерес. В настоящее время только значение -1 является допустимым.  
  
 `ptd`  
 Указывает [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) структуру, определяющую целевое устройство, для которого следует вернуть размер объекта.  
  
 `hicTargetDev`  
 Указывает информационный контекст для целевого устройства, указанного в `ptd` параметра, из которого объект может извлечь метрики устройства и тестирования возможности устройства. Если `ptd` — **NULL**, объект должен игнорировать значение в `hicTargetDev` параметр.  
  
 *pExtentInfo*  
 Указывает **DVEXTENTINFO** структура, которая задает данных. **DVEXTENTINFO** структуры:  
  
 `typedef struct  tagExtentInfo`  
  
 `{`  
  
 `UINT cb;`  
  
 `DWORD dwExtentMode;`  
  
 `SIZEL sizelProposed;`  
  
 `}   DVEXTENTINFO;`  
  
 Член структуры `dwExtentMode` может принимать одно из двух значений:  
  
- **DVEXTENT_CONTENT** запрос, как элемент управления должен быть точно по размеру содержимого (snap размер)  
  
- **DVEXTENT_INTEGRAL** при изменении размера, передать предложенный размер элемента управления  
  
 `psizel`  
 Указывает на изменение размера данных, возвращаемых элементом управления. Изменения размера возвращаемых данных имеет значение -1 для любого измерения, которое не было настроено.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если она успешно возвращает или изменяет размер; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию, чтобы вернуть размер объекта отображения ближайшим предложенный размер и степени режим в **DVEXTENTINFO** структуры. Реализация по умолчанию возвращает **FALSE** и делает без изменения размера.  
  
##  <a name="a-nameongetpredefinedstringsa--colecontrolongetpredefinedstrings"></a><a name="ongetpredefinedstrings"></a>COleControl::OnGetPredefinedStrings  
 Вызывается платформой для получения набора стандартных строк, представляющих возможные значения для свойства.  
  
```  
virtual BOOL OnGetPredefinedStrings(
    DISPID dispid,  
    CStringArray* pStringArray,  
    CDWordArray* pCookieArray);
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчера свойства элемента управления.  
  
 `pStringArray`  
 Массив строк, заполняется значением возвращают значения.  
  
 `pCookieArray`  
 A `DWORD` заполнено возвращаемые значения массива.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элементы были добавлены в `pStringArray` и `pCookieArray`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если элемент управления имеет свойство с набор возможных значений, которые могут быть представлены строками. Для каждого элемента, добавляемого `pStringArray`, следует добавить соответствующий элемент «cookie» для *pCookieArray.* Эти значения «cookie» позже может быть передан средой для `COleControl::OnGetPredefinedValue` функции.  
  
##  <a name="a-nameongetpredefinedvaluea--colecontrolongetpredefinedvalue"></a><a name="ongetpredefinedvalue"></a>COleControl::OnGetPredefinedValue  
 Вызывается платформой для получения значения, соответствующие одной из стандартных строк были возвращены переопределение `COleControl::OnGetPredefinedStrings`.  
  
```  
virtual BOOL OnGetPredefinedValue(
    DISPID dispid,  
    DWORD dwCookie,  
    VARIANT* lpvarOut);
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчера свойства элемента управления.  
  
 `dwCookie`  
 Значение файла cookie, ранее возвращенный переопределение `COleControl::OnGetPredefinedStrings`.  
  
 `lpvarOut`  
 Указатель на **VARIANT** структуры, через который будет возвращаться значение свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если возвращено в `lpvarOut`; в противном случае — 0.  
  
##  <a name="a-nameongetviewextenta--colecontrolongetviewextent"></a><a name="ongetviewextent"></a>COleControl::OnGetViewExtent  
 Вызывается средой в ответ на контейнер [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) запроса.  
  
```  
virtual BOOL OnGetViewExtent(
    DWORD dwDrawAspect,
    LONG lindex,
    DVTARGETDEVICE* ptd,
    LPSIZEL lpsizel);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDrawAspect*  
 `DWORD`описания формы или аспект, объекта будет отображаться. Допустимые значения берутся из перечисления [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) или **DVASPECT2**.  
  
 *Индекс*  
 Часть объекта, который представляет интерес. В настоящее время только&1; является допустимым.  
  
 `ptd`  
 Указывает [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) структуру, определяющую целевое устройство, для которого следует вернуть размер объекта.  
  
 *lpsizel*  
 Указывает расположение, место, куда возвращен размер объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сведения о степени успешно возвращен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если элемент управления использует два прохода рисования и ее непрозрачной и прозрачной части имеют разные измерения.  
  
##  <a name="a-nameongetviewrecta--colecontrolongetviewrect"></a><a name="ongetviewrect"></a>COleControl::OnGetViewRect  
 Вызывается средой в ответ на контейнер **IViewObjectEx::GetRect** запроса.  
  
```  
virtual BOOL OnGetViewRect(DWORD dwAspect, LPRECTL pRect);
```  
  
### <a name="parameters"></a>Параметры  
 `dwAspect`  
 `DWORD`описания формы или аспект, объекта будет отображаться. Допустимые значения берутся из перечисления [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) или **DVASPECT2**:  
  
- `DVASPECT_CONTENT`Ограничивающий прямоугольник для всего объекта. Верхний левый угол источника объекта и размер равен экстента, возвращенный **GetViewExtent***.*  
  
- **DVASPECT_OPAQUE** объекты с прямоугольной области непрозрачный возвращают этого прямоугольника. Остальные — ошибочными.  
  
- **DVASPECT_TRANSPARENT** прямоугольник, охватывающих все части прозрачный или нерегулярным.  
  
 `pRect`  
 Указывает [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907) структура прямоугольник, в котором должен быть нарисован объект. Этот параметр управляет размещением и Растягивание объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если размер объекта прямоугольника успешно возвращен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Размер объекта преобразуется в `OnGetViewRect` в прямоугольник, начиная с указанной позиции (значение по умолчанию — левом верхнем углу экрана). Переопределите эту функцию, если элемент управления использует два прохода рисования и ее непрозрачной и прозрачной части имеют разные измерения.  
  
##  <a name="a-nameongetviewstatusa--colecontrolongetviewstatus"></a><a name="ongetviewstatus"></a>COleControl::OnGetViewStatus  
 Вызывается средой в ответ на контейнер **IViewObjectEx::GetViewStatus** запроса.  
  
```  
virtual DWORD OnGetViewStatus();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из значений **Просмотр СОСТОЯНИЯ** перечисления в случае успешного выполнения; в противном случае — 0. Любое сочетание следующих доступны следующие значения:  
  
 **VIEWSTATUS_OPAQUE**  
 Объект является непрозрачным. Если этот бит не задано, объект содержит прозрачные детали. Этот бит применяется только аспекты, связанные с содержимым, а не к `DVASPECT_ICON` или `DVASPECT_DOCPRINT`.  
  
 **VIEWSTATUS_SOLIDBKGND**  
 Объект имеет непрозрачный фон (состоящую сплошным цветом, не узора кисти). Этот бит имеет смысл только если **VIEWSTATUS_OPAQUE** устанавливается и применяется только к аспекты, связанные с содержимым и не `DVASPECT_ICON` или `DVASPECT_DOCPRINT`.  
  
 **VIEWSTATUS_DVASPECTOPAQUE**  
 Поддерживает **DVASPECT_OPAQUE**. Все **IViewObjectEx** методов, которые принимают вид рисования, как параметр может быть вызван с этого аспекта.  
  
 **VIEWSTATUS_DVASPECTTRANSPARENT**  
 Поддерживает **DVASPECT_TRANSPARENT**. Все **IViewObjectEx** методов, которые принимают вид рисования, как параметр может быть вызван с этого аспекта.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если элемент управления использует два прохода рисования. Реализация по умолчанию возвращает **VIEWSTATUS_OPAQUE**.  
  
##  <a name="a-nameonhidetoolbarsa--colecontrolonhidetoolbars"></a><a name="onhidetoolbars"></a>COleControl::OnHideToolBars  
 Вызывается инфраструктурой при деактивации пользовательского интерфейса элемента управления.  
  
```  
virtual void OnHideToolBars();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация следует скрыть все панели инструментов, отображаются с `OnShowToolbars`.  
  
##  <a name="a-nameoninactivemousemovea--colecontroloninactivemousemove"></a><a name="oninactivemousemove"></a>COleControl::OnInactiveMouseMove  
 Вызывается контейнером для неактивных объектов под указателем мыши при получении `WM_MOUSEMOVE` сообщение.  
  
```  
virtual void OnInactiveMouseMove(
    LPCRECT lprcBounds,
    long x,
    long y,
    DWORD dwKeyState);
```  
  
### <a name="parameters"></a>Параметры  
 `lprcBounds`  
 Объект, ограничивающий прямоугольник в клиентских координатах окна. Указывает объекту его точное положение и размер на экране при `WM_MOUSEMOVE` было получено сообщение.  
  
 *x*  
 Координата x расположения мыши в клиентских координатах окна.  
  
 *y*  
 Y-координата расположения мыши в клиентских координатах окна.  
  
 `dwKeyState`  
 Указывает текущее состояние из сочетания клавиш на клавиатуре. Допустимые значения могут быть любые из флагов сочетание **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_BUTTON**, **MK_LBUTTON**, **MK_MBUTTON**, и **MK_RBUTTON**.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что клиентские координаты окна (в пикселях) используются для передачи позиции указателя мыши. Это стало возможным передавая ограничивающего прямоугольника объекта в одной системе координат.  
  
##  <a name="a-nameoninactivesetcursora--colecontroloninactivesetcursor"></a><a name="oninactivesetcursor"></a>COleControl::OnInactiveSetCursor  
 Вызывается контейнером для неактивных объектов под указателем мыши при получении `WM_SETCURSOR` сообщение.  
  
```  
virtual BOOL OnInactiveSetCursor(
    LPCRECT lprcBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL bSetAlways);
```  
  
### <a name="parameters"></a>Параметры  
 `lprcBounds`  
 Объект, ограничивающий прямоугольник в клиентских координатах окна. Указывает объекту его точное положение и размер на экране при `WM_SETCURSOR` было получено сообщение.  
  
 *x*  
 Координата x расположения мыши в клиентских координатах окна.  
  
 *y*  
 Y-координата расположения мыши в клиентских координатах окна.  
  
 *dwMouseMsg*  
 Идентификатор сообщения мыши, для которого `WM_SETCURSOR` произошла.  
  
 *bSetAlways*  
 Указывает, должен ли объект установите курсор. Если **TRUE**, объект должен установить курсор; Если **FALSE**, курсор не обязаны установите курсор и должен возвращать **S_FALSE** в этом случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что клиентские координаты окна (в пикселях) используются для передачи позиции указателя мыши. Это стало возможным передавая ограничивающего прямоугольника объекта в одной системе координат.  
  
##  <a name="a-nameonkeydowneventa--colecontrolonkeydownevent"></a><a name="onkeydownevent"></a>COleControl::OnKeyDownEvent  
 Вызывается платформой после обработки события KeyDown акций.  
  
```  
virtual void OnKeyDownEvent(
    USHORT nChar,  
    USHORT nShiftState);
```  
  
### <a name="parameters"></a>Параметры  
 `nChar`  
 Значение виртуальный код клавиши нажатой клавише. Список стандартных кодов виртуального ключа см. в разделе Winuser.h  
  
 `nShiftState`  
 Содержит сочетание следующих флагов.  
  
- **SHIFT_MASK** клавиша SHIFT была нажата в ходе выполнения действия.  
  
- **CTRL_MASK** клавиша CTRL была нажата в ходе выполнения действия.  
  
- **ALT_MASK** клавиша ALT была нажата в ходе выполнения действия.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если элементу управления требуется доступ к информации о ключе после инициировать событие.  
  
##  <a name="a-nameonkeypresseventa--colecontrolonkeypressevent"></a><a name="onkeypressevent"></a>COleControl::OnKeyPressEvent  
 Вызывается платформой после бумагу возникло событие KeyPress.  
  
```  
virtual void OnKeyPressEvent(USHORT nChar);
```  
  
### <a name="parameters"></a>Параметры  
 `nChar`  
 Содержит значение виртуальный код клавиши нажатой клавиши. Список стандартных кодов виртуального ключа см. в разделе Winuser.h  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что `nChar` значения были изменены в контейнере.  
  
 Переопределите эту функцию, если необходимо, чтобы уведомление после возникновения этого события.  
  
##  <a name="a-nameonkeyupeventa--colecontrolonkeyupevent"></a><a name="onkeyupevent"></a>COleControl::OnKeyUpEvent  
 Вызывается платформой после обработки события KeyDown акций.  
  
```  
virtual void OnKeyUpEvent(
    USHORT nChar,  
    USHORT nShiftState);
```  
  
### <a name="parameters"></a>Параметры  
 `nChar`  
 Значение виртуальный код клавиши нажатой клавише. Список стандартных кодов виртуального ключа см. в разделе Winuser.h  
  
 `nShiftState`  
 Содержит сочетание следующих флагов.  
  
- **SHIFT_MASK** клавиша SHIFT была нажата в ходе выполнения действия.  
  
- **CTRL_MASK** клавиша CTRL была нажата в ходе выполнения действия.  
  
- **ALT_MASK** клавиша ALT была нажата в ходе выполнения действия.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если элементу управления требуется доступ к информации о ключе после инициировать событие.  
  
##  <a name="a-nameonmappropertytopagea--colecontrolonmappropertytopage"></a><a name="onmappropertytopage"></a>COleControl::OnMapPropertyToPage  
 Вызывается платформой для получения идентификатора класса страницы свойств, который реализует редактирования указанного свойства.  
  
```  
virtual BOOL OnMapPropertyToPage(
    DISPID dispid,  
    LPCLSID lpclsid,  
    BOOL* pbPageOptional);
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчера свойства элемента управления.  
  
 `lpclsid`  
 Указатель на **CLSID** структуры, через который возвращается идентификатор класса.  
  
 *pbPageOptional*  
 Возвращает индикатор, использование указанного свойства страницы необязательно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если идентификатор класса был возвращен в `lpclsid`; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, чтобы предоставить способ вызова страницы свойств элемента управления в обозревателе свойств контейнера.  
  
##  <a name="a-nameonmnemonica--colecontrolonmnemonic"></a><a name="onmnemonic"></a>COleControl::OnMnemonic  
 Вызывается платформой, когда контейнер обнаружил, что была нажата назначенная клавиша элемента управления OLE.  
  
```  
virtual void OnMnemonic(LPMSG pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 `pMsg`  
 Указатель на сообщение Windows, созданное нажатием назначенной клавиши.  
  
##  <a name="a-nameonpropertiesa--colecontrolonproperties"></a><a name="onproperties"></a>COleControl::OnProperties  
 Вызывается платформой, когда контейнер был вызван глагол свойства элемента управления.  
  
```  
virtual BOOL OnProperties(
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMsg`  
 Указатель на сообщение Windows, которое вызвало команду.  
  
 `hWndParent`  
 Дескриптор родительского окна элемента управления.  
  
 `lpRect`  
 Указатель на прямоугольник, используемые элементом управления в контейнере.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если вызов будет выполнен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию отображает диалоговое окно свойств модальным.  
  
 Эта функция используется для отображения страницы свойств элемента управления. Вызовите `OnProperties` функции, передав дескриптор родительского элемента управления в `hWndParent` параметр. В этом случае значения `lpMsg` и `lpRect` параметры игнорируются.  
  
##  <a name="a-nameonqueryhitpointa--colecontrolonqueryhitpoint"></a><a name="onqueryhitpoint"></a>COleControl::OnQueryHitPoint  
 Вызывается средой в ответ на контейнер **IViewObjectEx::QueryHitPoint** запроса.  
  
```  
virtual BOOL OnQueryHitPoint(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG lCloseHint,
    DWORD* pHitResult);
```  
  
### <a name="parameters"></a>Параметры  
 `dwAspect`  
 Указывает способ представления объекта. Допустимые значения берутся из перечисления [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) или **DVASPECT2**.  
  
 `pRectBounds`  
 Указатель на `RECT` структура ограничивающий прямоугольник для клиентской области элемента управления OLE.  
  
 `ptlLoc`  
 Указатель на **ТОЧКИ** структура точки для проверки нажатия. Точка, задаваемая в координаты области клиента OLE.  
  
 `lCloseHint`  
 Расстояние, которое определяет «закрыть» к точке проверки на попадание.  
  
 `pHitResult`  
 Указатель на результат запроса попаданий. Одно из следующих значений:  
  
- **HITRESULT_OUTSIDE** `ptlLoc` находится за пределами OLE объекта, а не закрыто.  
  
- **HITRESULT_TRANSPARENT** *ptlLoc* находится в границах объекта OLE, но не близко к изображения. Например, может быть точку в середине прозрачный круг **HITRESULT_TRANSPARENT**.  
  
- **HITRESULT_CLOSE** `ptlLoc` — внутри или снаружи OLE-объект, но достаточно близко, считаются внутри объекта. Это значение может использоваться в небольших, тонкие и подробные объектов. Даже если точка находится за пределами ограничивающего прямоугольника объекта может по-прежнему находиться (это требуется для обращения небольших объектов).  
  
- **HITRESULT_HIT** `ptlLoc` находится в пределах изображения объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если результат нажатия успешно возвращен; в противном случае — 0. Попадание представляет собой объект наложения с область отображения элемента управления OLE.  
  
### <a name="remarks"></a>Примечания  
 Запросы, перекрывается ли прямоугольник отображения объекта заданной точки (достигает точки). `QueryHitPoint`можно переопределить для проверки попадания для непрямоугольных объектов.  
  
##  <a name="a-nameonqueryhitrecta--colecontrolonqueryhitrect"></a><a name="onqueryhitrect"></a>COleControl::OnQueryHitRect  
 Вызывается средой в ответ на контейнер **IViewObjectEx::QueryHitRect** запроса.  
  
```  
virtual BOOL OnQueryHitRect(
    DWORD dwAspect,  
    LPCRECT pRectBounds,  
    LPCRECT prcLoc,  
    LONG lCloseHint,  
    DWORD* pHitResult);
```  
  
### <a name="parameters"></a>Параметры  
 `dwAspect`  
 Указывает способ представления объекта. Допустимые значения берутся из перечисления [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) или **DVASPECT2**.  
  
 `pRectBounds`  
 Указатель на `RECT` структура ограничивающий прямоугольник для клиентской области элемента управления OLE.  
  
 *prcLoc*  
 Указатель на `RECT` структура прямоугольника для проверки попадания (перекрывающиеся прямоугольник объекта), относительно верхнего левого угла объекта.  
  
 `lCloseHint`  
 Не используется.  
  
 `pHitResult`  
 Указатель на результат запроса попаданий. Одно из следующих значений:  
  
- **HITRESULT_OUTSIDE** без точки в прямоугольнике попадания объектом OLE.  
  
- **HITRESULT_HIT** по крайней мере одну точку в прямоугольнике бы попадание в объекте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если результат нажатия успешно возвращен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Запросы, перекрывается ли прямоугольник отображения объекта любую точку в данном прямоугольнике (достигает прямоугольник). `QueryHitRect`можно переопределить для проверки попадания для непрямоугольных объектов.  
  
##  <a name="a-nameonrenderdataa--colecontrolonrenderdata"></a><a name="onrenderdata"></a>COleControl::OnRenderData  
 Вызывается платформой для получения данных в указанном формате.  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором запрашиваются сведения.  
  
 `lpStgMedium`  
 Указывает [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуры, в котором возвращаются данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат, помещенный в объект управления с помощью [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) или [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) функции-члены для отложенной обработки. Реализация по умолчанию эта функция вызывает `OnRenderFileData` или `OnRenderGlobalData`соответственно, если указанный носитель файле или памяти. Если запрошенный формат `CF_METAFILEPICT` или свойство persistent задать формат, реализация по умолчанию отображает соответствующие данные и возвращает ненулевое значение. В противном случае — возвращает значение 0 и не выполняет никаких действий.  
  
 Если *lpStgMedium-> tymed* — **TYMED_NULL**, **STGMEDIUM** следует выделить и заполняются в соответствии с *lpFormatEtc-> tymed*. Если не **TYMED_NULL**, **STGMEDIUM** должно быть заполнено месте с данными.  
  
 Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо. Если данные фиксированного размера и небольшой, переопределите `OnRenderGlobalData`. Если данные в файле или имеет переменный размер, переопределите `OnRenderFileData`.  
  
 Дополнительные сведения см. в разделе **FORMATETC** и **STGMEDIUM** структур в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonrenderfiledataa--colecontrolonrenderfiledata"></a><a name="onrenderfiledata"></a>COleControl::OnRenderFileData  
 Вызывается платформой для получения данных в указанном формате, если среда хранения представляет собой файл.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором запрашиваются сведения.  
  
 `pFile`  
 Указывает [CFile](../../mfc/reference/cfile-class.md) объект, в котором для визуализации данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат, помещенный в объект управления с помощью [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) функции-члена для отложенной подготовки к просмотру. Реализация по умолчанию эта функция просто возвращает **FALSE**.  
  
 Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо. Если требуется обрабатывать несколько носителей, переопределить `OnRenderData`. Если данные в файле или имеет переменный размер, переопределите `OnRenderFileData`.  
  
 Дополнительные сведения см. в разделе **FORMATETC** в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonrenderglobaldataa--colecontrolonrenderglobaldata"></a><a name="onrenderglobaldata"></a>COleControl::OnRenderGlobalData  
 Вызывается платформой для получения данных в указанном формате, если указанный носитель является глобальной памяти.  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указывает [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат, в котором запрашиваются сведения.  
  
 `phGlobal`  
 Указывает дескриптор глобальной памяти, в котором не возвращаются данные. Если выделена память, этот параметр может иметь **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Указанный формат, помещенный в объект управления с помощью [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) функции-члена для отложенной подготовки к просмотру. Реализация по умолчанию эта функция просто возвращает **FALSE**.  
  
 Если `phGlobal` — **NULL**, затем новый `HGLOBAL` следует выделить и возвращается в `phGlobal`. В противном случае — `HGLOBAL` определяется `phGlobal` должен быть заполнен данными. Объем данных, помещаются в `HGLOBAL` не должен превышать текущий размер блока памяти. Кроме того блок не может быть перемещен до большего размера.  
  
 Переопределите эту функцию для предоставления данных в запрошенном пользователем формате и средних. В зависимости от данных может потребоваться переопределить один из версии этих функций вместо. Если требуется обрабатывать несколько носителей, переопределить `OnRenderData`. Если данные в файле или имеет переменный размер, переопределите `OnRenderFileData`.  
  
 Дополнительные сведения см. в разделе **FORMATETC** в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonresetstatea--colecontrolonresetstate"></a><a name="onresetstate"></a>COleControl::OnResetState  
 Вызывается платформой, если свойства элемента управления должны быть установлены в значения по умолчанию.  
  
```  
virtual void OnResetState();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает [DoPropExchange](#dopropexchange), передав `CPropExchange` объекта, который вызывает свойства, чтобы задать значения по умолчанию.  
  
 Модуль записи элемент управления можно вставить код инициализации для элемента управления OLE в этом переопределяемыми. Эта функция вызывается, когда [IPersistStream::Load](http://msdn.microsoft.com/library/windows/desktop/ms680568) или [IPersistStorage::Load](http://msdn.microsoft.com/library/windows/desktop/ms680557) завершается ошибкой, или [IPersistStreamInit::InitNew](http://msdn.microsoft.com/library/windows/desktop/ms690234) или [IPersistStorage::InitNew](http://msdn.microsoft.com/library/windows/desktop/ms687194) вызывается без вызова либо **IPersistStream::Load** или **IPersistStorage::Load**.  
  
##  <a name="a-nameonsetclientsitea--colecontrolonsetclientsite"></a><a name="onsetclientsite"></a>COleControl::OnSetClientSite  
 Вызывается платформой, когда контейнер элемента управления называется **IOleControl::SetClientSite** функции.  
  
```  
virtual void OnSetClientSite();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `OnSetClientSite` проверяет, загружены ли свойства пути данных и если это так, вызывается `DoDataPathPropExchange`.  
  
 Переопределите эту функцию для выполнения специальной обработки этого уведомления. В частности переопределения этой функции следует вызвать базовый класс.  
  
##  <a name="a-nameonsetdataa--colecontrolonsetdata"></a><a name="onsetdata"></a>COleControl::OnSetData  
 Вызывается платформой для замены данных элемента управления с заданными данными.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```  
  
### <a name="parameters"></a>Параметры  
 `lpFormatEtc`  
 Указатель на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структура, задающая формат данных.  
  
 `lpStgMedium`  
 Указатель на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) структуры, в которой хранятся данные.  
  
 `bRelease`  
 **Значение TRUE,** Если элемент управления должен освободить среду хранения; **FALSE** Если элемент управления не должен освободить среду хранения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если данные в свойстве постоянного задается формат, реализация по умолчанию соответствующим образом изменяет состояние элемента управления. В противном случае реализация по умолчанию не выполняет никаких действий. Если `bRelease` — **TRUE**, затем вызов **ReleaseStgMedium** осуществляется; в противном случае не.  
  
 Переопределите эту функцию для замены данных элемента управления с заданными данными.  
  
 Дополнительные сведения см. в разделе **FORMATETC** и **STGMEDIUM** структур в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonsetextenta--colecontrolonsetextent"></a><a name="onsetextent"></a>COleControl::OnSetExtent  
 Вызывается инфраструктурой при область элемента управления должно быть изменено, в результате вызова [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330).  
  
```  
virtual BOOL OnSetExtent(LPSIZEL lpSizeL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpSizeL`  
 Указатель на **размера** структуру, которая использует длинных целых чисел для представления ширину и высоту элемента управления, выраженное в **HIMETRIC** единиц.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если изменение размера был принят; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию обрабатывает изменения размеров элемента управления экстента. Если элемент управления является активным на месте, вызов в контейнер **OnPosRectChanged** становится.  
  
 Переопределите эту функцию для изменения размеров элемента управления по умолчанию.  
  
##  <a name="a-nameonsetobjectrectsa--colecontrolonsetobjectrects"></a><a name="onsetobjectrects"></a>COleControl::OnSetObjectRects  
 Вызывается платформой для реализации вызов [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767).  
  
```  
virtual BOOL OnSetObjectRects(
    LPCRECT lpRectPos,  
    LPCRECT lpRectClip);
```  
  
### <a name="parameters"></a>Параметры  
 *lpRectPos*  
 Указатель на структуру RECT, определяющее новое положение и размер относительно контейнера элемента управления.  
  
 `lpRectClip`  
 Указатель на `RECT` структуру указывая прямоугольной области, в которую будет обрезан элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если изменение положения был принят; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию автоматически обрабатывает изменения положения и размера окна элемента управления и возвращает **TRUE**.  
  
 Переопределите эту функцию, чтобы изменить поведение по умолчанию для данной функции.  
  
##  <a name="a-nameonshowtoolbarsa--colecontrolonshowtoolbars"></a><a name="onshowtoolbars"></a>COleControl::OnShowToolBars  
 Вызывается платформой после активации пользовательского интерфейса для элемента управления.  
  
```  
virtual void OnShowToolBars();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не выполняет никаких действий.  
  
##  <a name="a-nameontextchangeda--colecontrolontextchanged"></a><a name="ontextchanged"></a>COleControl::OnTextChanged  
 Вызывается инфраструктурой при изменении стандартных значение свойства заголовок или текст.  
  
```  
virtual void OnTextChanged();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает `InvalidateControl`.  
  
 Если уведомление после изменения этого свойства требуется переопределите эту функцию.  
  
##  <a name="a-nameonwindowlessmessagea--colecontrolonwindowlessmessage"></a><a name="onwindowlessmessage"></a>COleControl::OnWindowlessMessage  
 Вызывается средой в ответ на контейнер **IOleInPlaceObjectWindowless::OnWindowMessage** запроса.  
  
```  
virtual BOOL OnWindowlessMessage(
    UINT msg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* plResult);
```  
  
### <a name="parameters"></a>Параметры  
 `msg`  
 Идентификатор сообщения при передаче по Windows.  
  
 `wParam`  
 Как передавать по Windows. Задает дополнительные сведения для конкретного сообщения. Содержимое этого параметра зависит от значения `msg` параметр.  
  
 `lParam`  
 Как передавать по Windows. Задает дополнительные сведения для конкретного сообщения. Содержимое этого параметра зависит от значения `msg` параметр.  
  
 *plResult*  
 Код результата Windows. Указывает результат обработки сообщения и зависит от отправленного сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Обрабатывает сообщения окна для элементов управления без окон. `COleControl`в `OnWindowlessMessage` можно использовать для окна сообщения, отличные от сообщения мыши и клавиатуры. `COleControl`предоставляет [SetCapture](#setcapture) и [SetFocus](#setfocus) специально для получения фокуса клавиатуры и захвата мыши безоконный OLE-объекты.  
  
 Поскольку объекты без окон не имеют окна, им требуется механизм для диспетчеризации сообщений контейнера к ним. Безоконный OLE-объект получает сообщения из контейнера, через `OnWindowMessage` метод `IOleInPlaceObjectWindowless` интерфейса (расширение [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) безоконный поддержки). `OnWindowMessage`не принимает `HWND` параметр.  
  
##  <a name="a-nameparenttoclienta--colecontrolparenttoclient"></a><a name="parenttoclient"></a>COleControl::ParentToClient  
 Преобразует координаты `pPoint` в клиентских координатах.  
  
```  
virtual UINT ParentToClient(
    LPCRECT lprcBounds,
    LPPOINT pPoint,
    BOOL bHitTest = FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lprcBounds`  
 Указатель на границы элемента управления OLE в контейнере. Области всего элемента управления, включая границами и полосами прокрутки, но не клиентской области.  
  
 `pPoint`  
 Указатель на родительский (контейнер) укажите преобразуются в координаты клиентской области элемента управления.  
  
 `bHitTest`  
 Указывает ли попадания на точку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если `bHitTest` — **FALSE**, возвращает **HTNOWHERE**. Если `bHitTest` — **TRUE**возвращает расположение, в котором родительский (контейнер) точки посадки в клиентской области элемента управления OLE и является одним из следующих мыши попадания значения:  
  
- **HTBORDER** в границы окна, у которых нет границы для изменения размера.  
  
- **HTBOTTOM** в нижнем горизонтальной границы окна.  
  
- **HTBOTTOMLEFT** в левом нижнем углу границы окна.  
  
- **HTBOTTOMRIGHT** в нижнем правом углу границы окна.  
  
- **HTCAPTION** в области заголовка.  
  
- **HTCLIENT** в клиентской области.  
  
- **HTERROR** на заднем плане экрана или Разделительная линия между windows (то же, что **HTNOWHERE** за исключением того, что **DefWndProc** функции Windows выдает звуковой сигнал в случае ошибки).  
  
- **HTGROWBOX** в поле размер.  
  
- **HTHSCROLL** в горизонтальной полосы прокрутки.  
  
- **HTLEFT** в левой границы окна.  
  
- **HTMAXBUTTON** кнопка в максимизации.  
  
- **HTMENU** в области меню.  
  
- **HTMINBUTTON** кнопки в свести к минимуму.  
  
- **HTNOWHERE** на заднем плане экрана или Разделительная линия между windows.  
  
- **HTREDUCE** кнопки в свести к минимуму.  
  
- **HTRIGHT** в правую границу окна.  
  
- **HTSIZE** в поле размер (то же, что **HTGROWBOX**).  
  
- **HTSYSMENU** в оконном меню или кнопку «Close» в дочернем окне.  
  
- **HTTOP** в верхнем горизонтальной границы окна.  
  
- **HTTOPLEFT** в левом верхнем углу границы окна.  
  
- **HTTOPRIGHT** в правом верхнем углу границы окна.  
  
- **HTTRANSPARENT** в окно закрывается другим окном.  
  
- **HTVSCROLL** на вертикальной полосе прокрутки.  
  
- **HTZOOM** кнопка в максимизации.  
  
### <a name="remarks"></a>Примечания  
 На входе `pPoint` относительно начала координат родительского объекта (верхний левый угол контейнера). На выходе `pPoint` относительно начала координат клиентской области элемента управления OLE (верхний левый угол клиентской области элемента управления).  
  
##  <a name="a-namepostmodaldialoga--colecontrolpostmodaldialog"></a><a name="postmodaldialog"></a>COleControl::PostModalDialog  
 Уведомляет контейнера закрыт модального диалогового окна.  
  
```  
void PostModalDialog(HWND hWndParent = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 Дескриптор родительского окна модальным диалоговым окном.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после отображения любой модальным диалоговым окном. Эту функцию необходимо вызывать, чтобы контейнер можно включить любой окон верхнего уровня, отключить, `PreModalDialog`. Эта функция должна составлять пару с вызова `PreModalDialog`.  
  
##  <a name="a-namepremodaldialoga--colecontrolpremodaldialog"></a><a name="premodaldialog"></a>COleControl::PreModalDialog  
 Уведомляет контейнер, в котором модального диалогового окна будет отображаться.  
  
```  
void PreModalDialog(HWND hWndParent = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 Дескриптор родительского окна модальным диалоговым окном.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается перед отображением любой модальным диалоговым окном. Эту функцию необходимо вызывать, чтобы контейнер можно отключить все его окон верхнего уровня. После отображения модального диалогового окна необходимо вызвать `PostModalDialog`.  
  
##  <a name="a-namerecreatecontrolwindowa--colecontrolrecreatecontrolwindow"></a><a name="recreatecontrolwindow"></a>COleControl::RecreateControlWindow  
 Удаляет и повторно создает окна элемента управления.  
  
```  
void RecreateControlWindow();
```  
  
### <a name="remarks"></a>Примечания  
 Это может потребоваться, если необходимо изменить битов стиля окна.  
  
##  <a name="a-namerefresha--colecontrolrefresh"></a><a name="refresh"></a>COleControl::Refresh  
 Вызывает перерисовку элемента управления OLE.  
  
```  
void Refresh();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция поддерживается `COleControl` базового класса как акций метод, именуемый обновления. Это позволяет пользователям элемента управления OLE для отрисовки элемента управления в определенное время. Дополнительные сведения об этом методе см. в статье [элементы управления ActiveX: методы](../../mfc/mfc-activex-controls-methods.md).  
  
##  <a name="a-namereleasecapturea--colecontrolreleasecapture"></a><a name="releasecapture"></a>COleControl::ReleaseCapture  
 Освобождает захват мыши.  
  
```  
BOOL ReleaseCapture();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления обладает захвата мыши, захвата освобождается. В противном случае эта функция не оказывает влияния.  
  
##  <a name="a-namereleasedca--colecontrolreleasedc"></a><a name="releasedc"></a>COleControl::ReleaseDC  
 Освобождает контекст устройства отображения контейнера безоконный элемент управления, освобождая контекст устройства для использования другими приложениями.  
  
```  
int ReleaseDC(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Определяет контекст устройства контейнером выпуска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Приложение должно вызвать `ReleaseDC` для каждого вызова [GetDC](#getdc).  
  
##  <a name="a-namereparentcontrolwindowa--colecontrolreparentcontrolwindow"></a><a name="reparentcontrolwindow"></a>COleControl::ReparentControlWindow  
 Задает родительский объект элемента управления.  
  
```  
virtual void ReparentControlWindow(
    HWND hWndOuter,  
    HWND hWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 *hWndOuter*  
 Дескриптор окна элемента управления.  
  
 `hWndParent`  
 Дескриптор родительского окна новый.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для сброса родительского окна элемента управления.  
  
##  <a name="a-nameresetstockpropsa--colecontrolresetstockprops"></a><a name="resetstockprops"></a>COleControl::ResetStockProps  
 Инициализирует состояние `COleControl` стандартные свойства до значений по умолчанию.  
  
```  
void ResetStockProps();
```  
  
### <a name="remarks"></a>Примечания  
 Свойства являются: внешний вид, BackColor, BorderStyle, заголовок, включено, шрифт, цвет переднего плана, hWnd и текст. Описание стандартных свойств см. в разделе [элементы управления ActiveX: Добавление свойства запасов](../../mfc/mfc-activex-controls-adding-stock-properties.md).  
  
 Можно повысить производительность двоичные инициализации элемента управления с помощью `ResetStockProps` и `ResetVersion` переопределение `COleControl::OnResetState`. См. следующий пример. Дополнительные сведения об оптимизации инициализации см [элементы управления ActiveX: оптимизация](../../mfc/mfc-activex-controls-optimization.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAxCtl&#7;](../../mfc/reference/codesnippet/cpp/colecontrol-class_8.cpp)]  
  
##  <a name="a-nameresetversiona--colecontrolresetversion"></a><a name="resetversion"></a>COleControl::ResetVersion  
 Инициализирует номер версии для указанного значения.  
  
```  
void ResetVersion(DWORD dwVersionDefault);
```  
  
### <a name="parameters"></a>Параметры  
 `dwVersionDefault`  
 Номер версии для назначения элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Можно повысить производительность двоичные инициализации элемента управления с помощью `ResetVersion` и `ResetStockProps` переопределение `COleControl::OnResetState`. Можно найти в [ResetStockProps](#resetstockprops). Дополнительные сведения об оптимизации инициализации см [элементы управления ActiveX: оптимизация](../../mfc/mfc-activex-controls-optimization.md).  
  
##  <a name="a-namescrollwindowa--colecontrolscrollwindow"></a><a name="scrollwindow"></a>COleControl::ScrollWindow  
 Позволяет без окон OLE-объект для прокрутки области в ее на месте активного изображения на экране.  
  
```  
void ScrollWindow(
    int xAmount,
    int yAmount,
    LPCRECT lpRect = NULL,
    LPCRECT lpClipRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `xAmount`  
 Уровень устройства единиц, горизонтальной прокрутки. Этот параметр должен иметь отрицательное значение для прокрутки влево.  
  
 `yAmount`  
 Уровень устройства единиц, вертикальной прокрутки. Этот параметр должен иметь отрицательное значение для прокрутки вверх.  
  
 `lpRect`  
 Указывает [CRect](../../atl-mfc-shared/reference/crect-class.md) объект или структуру RECT, которая задает часть клиентской области объекта OLE для прокрутки, в клиентских координатах окна. Если `lpRect` — **NULL**, прокручивать весь объект OLE клиентской области.  
  
 `lpClipRect`  
 Указывает `CRect` объекта или `RECT` структуру, которая задает прямоугольник, клип. Прокручены только пиксели внутри прямоугольника. Биты вне прямоугольника не затрагиваются, даже если они находятся в `lpRect` прямоугольник. Если `lpClipRect` — **NULL**, отсечение не выполняется на прямоугольник прокрутки.  
  
##  <a name="a-nameselectfontobjecta--colecontrolselectfontobject"></a><a name="selectfontobject"></a>COleControl::SelectFontObject  
 Выбирает шрифт в контекст устройства.  
  
```  
CFont* SelectFontObject(
    CDC* pDC,  
    CFontHolder& fontHolder);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на объект контекста устройства.  
  
 `fontHolder`  
 Ссылка на [CFontHolder](../../mfc/reference/cfontholder-class.md) объект, представляющий шрифт для выбора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на ранее выбранный шрифт. После завершения всех операций рисования, использующих вызывающий *fontHolder,* его следует повторно выбрать ранее выбранный шрифт, передав в качестве параметра [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject).  
  
##  <a name="a-nameselectstockfonta--colecontrolselectstockfont"></a><a name="selectstockfont"></a>COleControl::SelectStockFont  
 Выбирает свойство Font в контексте устройства.  
  
```  
CFont* SelectStockFont(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Контекст устройства, в который будет выбран шрифт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на ранее выбранным `CFont` объекта. Следует использовать [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) установите этот шрифт обратно в контекст устройства, при завершении.  
  
##  <a name="a-nameserializeextenta--colecontrolserializeextent"></a><a name="serializeextent"></a>COleControl::SerializeExtent  
 Сериализует или инициализирует состояние отображения пространство, отведенное для элемента управления.  
  
```  
void SerializeExtent(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 `ar`  
 Объект `CArchive` объект для сериализации в.  
  
### <a name="remarks"></a>Примечания  
 Можно повысить производительность двоичные сохраняемости элемента управления с помощью `SerializeExtent`, `SerializeStockProps`, и `SerializeVersion` переопределение **COleControl::Serialize**. См. следующий пример. Дополнительные сведения об оптимизации инициализации см [элементы управления ActiveX: оптимизация](../../mfc/mfc-activex-controls-optimization.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAxCtl №&8;](../../mfc/reference/codesnippet/cpp/colecontrol-class_9.cpp)]  
  
##  <a name="a-nameserializestockpropsa--colecontrolserializestockprops"></a><a name="serializestockprops"></a>COleControl::SerializeStockProps  
 Сериализует или инициализирует состояние `COleControl` стандартные свойства: внешний вид, BackColor, BorderStyle, заголовок, включено, шрифт, цвет переднего плана и текста.  
  
```  
void SerializeStockProps(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 `ar`  
 Объект `CArchive` объект для сериализации в.  
  
### <a name="remarks"></a>Примечания  
 Описание стандартных свойств см. в разделе [элементы управления ActiveX: Добавление свойства запасов](../../mfc/mfc-activex-controls-adding-stock-properties.md).  
  
 Можно повысить производительность двоичные сохраняемости элемента управления с помощью `SerializeStockProps`, `SerializeExtent`, и `SerializeVersion` переопределение **COleControl::Serialize**. Например, узнать код [SerializeExtent](#serializeextent). Дополнительные сведения об оптимизации инициализации см [элементы управления ActiveX: оптимизация](../../mfc/mfc-activex-controls-optimization.md).  
  
##  <a name="a-nameserializeversiona--colecontrolserializeversion"></a><a name="serializeversion"></a>COleControl::SerializeVersion  
 Сериализует или инициализирует состояние сведения о версии элемента управления.  
  
```  
DWORD SerializeVersion(
    CArchive& ar,
    DWORD dwVersionDefault,
    BOOL bConvert = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `ar`  
 Объект `CArchive` объект для сериализации в.  
  
 `dwVersionDefault`  
 Номер текущей версии элемента управления.  
  
 `bConvert`  
 Указывает, является ли постоянных данных должны быть преобразованы в формат последней версии при его сохранении, или сохраняется в том же формате, что при его загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер версии элемента управления. Если загрузка архива, `SerializeVersion` возвращает версии, загруженной из этого архива. В противном случае — возвращает текущую загруженную версию.  
  
### <a name="remarks"></a>Примечания  
 Можно повысить производительность двоичные сохраняемости элемента управления с помощью `SerializeVersion`, `SerializeExtent`, и `SerializeStockProps` переопределение **COleControl::Serialize**. Например, узнать код [SerializeExtent](#serializeextent). Дополнительные сведения об оптимизации инициализации см [элементы управления ActiveX: оптимизация](../../mfc/mfc-activex-controls-optimization.md).  
  
##  <a name="a-namesetappearancea--colecontrolsetappearance"></a><a name="setappearance"></a>COleControl::SetAppearance  
 Задает значение свойства акций внешний вид элемента управления.  
  
```  
void SetAppearance (short sAppearance);
```  
  
### <a name="parameters"></a>Параметры  
 *sAppearance*  
 Объект **короткие** ( `VT_I2`) значение, которое используется для внешнего вида элемента управления. Нулевое значение задает внешний вид элемента управления неструктурированными и значение 1 задает внешний вид элемента управления с трехмерной графикой.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о свойствах хранения см. в разделе [элементы управления ActiveX: свойства](../../mfc/mfc-activex-controls-properties.md).  
  
##  <a name="a-namesetbackcolora--colecontrolsetbackcolor"></a><a name="setbackcolor"></a>COleControl::SetBackColor  
 Задает значение свойства акций BackColor элемента управления.  
  
```  
void SetBackColor(OLE_COLOR dwBackColor);
```  
  
### <a name="parameters"></a>Параметры  
 *dwBackColor*  
 **OLE_COLOR** значение, которое используется для рисования элемента управления фона.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения об использовании этого свойства и других связанных свойств, см. в статье [элементы управления ActiveX: свойства](../../mfc/mfc-activex-controls-properties.md).  
  
##  <a name="a-namesetborderstylea--colecontrolsetborderstyle"></a><a name="setborderstyle"></a>COleControl::SetBorderStyle  
 Задает значение акций BorderStyle свойства элемента управления.  
  
```  
void SetBorderStyle(short sBorderStyle);
```  
  
### <a name="parameters"></a>Параметры  
 *sBorderStyle*  
 Новый стиль границы для элемента управления; 0 означает без границы, а 1 — обычный границы.  
  
### <a name="remarks"></a>Примечания  
 Окно управления будут повторно созданы и `OnBorderStyleChanged` именем.  
  
##  <a name="a-namesetcapturea--colecontrolsetcapture"></a><a name="setcapture"></a>COleControl::SetCapture  
 В результате окна контейнера элемента управления необходимо выполнить владения захвата мыши на имени элемента управления.  
  
```  
CWnd* SetCapture();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на **CWnd** объект window, ранее получивший ввод от мыши.  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления активирован и без окон, эта функция приводит окна контейнера элемента управления необходимо выполнить владения захвата мыши на имени элемента управления. В противном случае, эта функция приводит самим вступили в распоряжении захвата мыши элементом управления (то же, что `CWnd::SetCapture`).  
  
##  <a name="a-namesetcontrolsizea--colecontrolsetcontrolsize"></a><a name="setcontrolsize"></a>COleControl::SetControlSize  
 Задает размер окна элемента управления OLE и уведомляет контейнер, в котором сайт элемента управления изменяется.  
  
```  
BOOL SetControlSize(int cx, int cy);
```  
  
### <a name="parameters"></a>Параметры  
 `cx`  
 Ширина нового элемента управления в пикселях.  
  
 `cy`  
 Задает новую высоту элемента управления в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если вызов был успешным; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не должна использоваться в конструкторе элемента управления.  
  
 Обратите внимание, что все координаты для управления windows относительно верхнего левого угла элемента управления.  
  
##  <a name="a-namesetenableda--colecontrolsetenabled"></a><a name="setenabled"></a>COleControl::SetEnabled  
 Задает значение свойства Enabled элемента управления акции.  
  
```  
void SetEnabled(BOOL bEnabled);
```  
  
### <a name="parameters"></a>Параметры  
 `bEnabled`  
 **Значение TRUE,** Если элемент управления включен; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 После установки этого свойства **OnEnabledChange** вызывается.  
  
##  <a name="a-namesetfocusa--colecontrolsetfocus"></a><a name="setfocus"></a>COleControl::SetFocus  
 В результате элемент управления контейнера окно владение фокус ввода от имени элемента управления.  
  
```  
CWnd* SetFocus();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на **CWnd** объект window, ранее имевший фокус ввода, или **NULL** Если окна нет.  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления активирован и без окон, эта функция приводит элемент управления контейнера окно владение фокус ввода, от имени элемента управления. Фокус ввода направляет ввод с клавиатуры в окно контейнера и контейнера передает все сообщения клавиатуры последующих OLE-объекта, который вызывает `SetFocus`. Любое окно, ранее имевший фокус ввода теряет его.  
  
 Если элемент управления не без окон, эта функция вызывает сам воспользоваться владение фокус ввода (то же, что `CWnd::SetFocus`).  
  
##  <a name="a-namesetfonta--colecontrolsetfont"></a><a name="setfont"></a>COleControl::SetFont  
 Задает свойство Font элемента управления.  
  
```  
void SetFont(LPFONTDISP pFontDisp);
```  
  
### <a name="parameters"></a>Параметры  
 *pFontDisp*  
 Указатель на интерфейс диспетчеризации шрифта.  
  
##  <a name="a-namesetforecolora--colecontrolsetforecolor"></a><a name="setforecolor"></a>COleControl::SetForeColor  
 Задает значение свойства акций цвет переднего плана элемента управления.  
  
```  
void SetForeColor(OLE_COLOR dwForeColor);
```  
  
### <a name="parameters"></a>Параметры  
 *dwForeColor*  
 **OLE_COLOR** значение, которое используется для рисования элемента управления переднего плана.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения об использовании этого свойства и других связанных свойств, см. в статье [элементы управления ActiveX: свойства](../../mfc/mfc-activex-controls-properties.md).  
  
##  <a name="a-namesetinitialdataformatsa--colecontrolsetinitialdataformats"></a><a name="setinitialdataformats"></a>COleControl::SetInitialDataFormats  
 Вызывается платформой для инициализации список форматов данных, поддерживаемый данным элементом управления.  
  
```  
virtual void SetInitialDataFormats();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию задает два формата: `CF_METAFILEPICT` и постоянное свойство.  
  
##  <a name="a-namesetinitialsizea--colecontrolsetinitialsize"></a><a name="setinitialsize"></a>COleControl::SetInitialSize  
 Задает размер элемента управления OLE, при первом отображении в контейнере.  
  
```  
void SetInitialSize(
    int cx,  
    int cy);
```  
  
### <a name="parameters"></a>Параметры  
 `cx`  
 Исходная ширина элемента управления OLE, в пикселях.  
  
 `cy`  
 Исходную высоту элемента управления OLE, в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается в конструкторе таким образом, чтобы задать начальный размер элемента управления. Начальный размер измеряется в единицы устройства или пикселей. Рекомендуется, соответствующий вызов в конструктор элемента управления.  
  
##  <a name="a-namesetmodifiedflaga--colecontrolsetmodifiedflag"></a><a name="setmodifiedflag"></a>COleControl::SetModifiedFlag  
 Изменяет измененном состоянии элемента управления.  
  
```  
void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bModified`  
 Новое значение для элемента управления модифицированная флаг. **Значение TRUE,** указывает, что состояние элемента управления был изменен; **FALSE** показывает, что состояние элемента управления просто сохранен.  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции при каждом изменении, может повлиять на постоянное состояние элемента управления. Например, при изменении значения свойства постоянного вызвать эту функцию с `bModified` **TRUE**.  
  
##  <a name="a-namesetnotpermitteda--colecontrolsetnotpermitted"></a><a name="setnotpermitted"></a>COleControl::SetNotPermitted  
 Указывает, что произошел сбой запроса на изменение.  
  
```  
void SetNotPermitted();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается, когда `BoundPropertyRequestEdit` завершается ошибкой. Эта функция создает исключение типа **COleDispScodeException** для указания набора операция не была разрешена.  
  
##  <a name="a-namesetnotsupporteda--colecontrolsetnotsupported"></a><a name="setnotsupported"></a>COleControl::SetNotSupported  
 Предотвращает изменение значения свойства элемента управления для пользователя.  
  
```  
void SetNotSupported();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вместо функцию набор любое свойство, где не поддерживается изменение значения свойства элемента управления пользователем. Примером может служить свойство, которое доступно только для чтения.  
  
##  <a name="a-namesetrectincontainera--colecontrolsetrectincontainer"></a><a name="setrectincontainer"></a>COleControl::SetRectInContainer  
 Задает координаты прямоугольника элемента управления относительно контейнера, выраженный в единицах измерения устройства.  
  
```  
BOOL SetRectInContainer(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpRect`  
 Указатель на прямоугольник, содержащий новые координаты элемента управления относительно контейнера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если вызов был успешным; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления является открытым, оно изменяется; в противном случае контейнера **OnPosRectChanged** вызывается функция.  
  
##  <a name="a-namesettexta--colecontrolsettext"></a><a name="settext"></a>COleControl::SetText  
 Задает значение акций заголовок или текст свойства элемента управления.  
  
```  
void SetText(LPCTSTR pszText);
```  
  
### <a name="parameters"></a>Параметры  
 `pszText`  
 Указатель на строку знаков.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что стандартных свойств заголовок и текст и сопоставлены с тем же значением. Это означает, что любые изменения любого из этих свойств будет автоматически изменяться оба свойства. Как правило элемент управления должен поддерживать акции заголовок или свойства Text, но не оба.  
  
##  <a name="a-namethrowerrora--colecontrolthrowerror"></a><a name="throwerror"></a>COleControl::ThrowError  
 Указывает на возникновение ошибки в элементе управления.  
  
```  
void ThrowError(
    SCODE sc,  
    UINT nDescriptionID,  
    UINT nHelpID = -1);

 
void ThrowError(
    SCODE sc,  
    LPCTSTR pszDescription = NULL,  
    UINT nHelpID = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `sc`  
 Значение кода состояния для создания отчета. Полный список возможных кодов см. в статье [элементы управления ActiveX: Дополнительные темы](../../mfc/mfc-activex-controls-advanced-topics.md).  
  
 `nDescriptionID`  
 Идентификатор строкового ресурса исключения для создания отчета.  
  
 `nHelpID`  
 Идентификатор справки раздела для создания отчета.  
  
 `pszDescription`  
 Строка, содержащая описание исключения для создания отчета.  
  
### <a name="remarks"></a>Примечания  
 Эта функция должна вызываться только из функции Get или Set для свойства OLE или реализации метода автоматизации OLE. Если возникает необходимость оповестить ошибки, возникающие в других случаях, должен срабатывать акций события ошибки.  
  
##  <a name="a-nametransformcoordsa--colecontroltransformcoords"></a><a name="transformcoords"></a>COleControl::TransformCoords  
 Значения между координат преобразований **HIMETRIC** и собственного контейнера единицами измерения.  
  
```  
void TransformCoords(
    POINTL* lpptlHimetric,  
    POINTF* lpptfContainer,  
    DWORD flags);
```  
  
### <a name="parameters"></a>Параметры  
 *lpptlHimetric*  
 Указатель на **POINTL** структура, содержащая координаты в **HIMETRIC** единиц.  
  
 *lpptfContainer*  
 Указатель на **POINTF** структура, содержащая координаты в размер единицы контейнера.  
  
 `flags`  
 Комбинация следующих значений:  
  
- **XFORMCOORDS_POSITION** положение в контейнере.  
  
- **XFORMCOORDS_SIZE** размер в контейнере.  
  
- **XFORMCOORDS_HIMETRICTOCONTAINER** преобразования **HIMETRIC** единицы контейнера единиц.  
  
- **XFORMCOORDS_CONTAINERTOHIMETRIC** преобразование единиц контейнера **HIMETRIC** единиц.  
  
### <a name="remarks"></a>Примечания  
 Первые два флаги **XFORMCOORDS_POSITION** и **XFORMCOORDS_SIZE**, указывают ли координаты должны рассматриваться как положение или размер. Оставшиеся два флаги указывают направление преобразования.  
  
##  <a name="a-nametranslatecolora--colecontroltranslatecolor"></a><a name="translatecolor"></a>COleControl::TranslateColor  
 Преобразует значение цвета из **OLE_COLOR** тип данных для [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) тип данных.  
  
```  
COLORREF TranslateColor(
    OLE_COLOR clrColor,  
    HPALETTE hpal = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `clrColor`  
 Объект **OLE_COLOR** тип данных. Дополнительные сведения см. в разделе Windows [OleTranslateColor](http://msdn.microsoft.com/library/windows/desktop/ms694353) функции.  
  
 `hpal`  
 Дескриптор палитры необязательно; может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение 32-разрядный цвет RGB (красный, зеленый, синий), которое определяет надежной цвет, ближайший к `clrColor` значению, которое можно представить устройства.  
  
### <a name="remarks"></a>Примечания  
 Эта функция полезна для преобразования стандартных свойств основной цвет и цвет фона для **COLORREF** типы, используемые [CDC](../../mfc/reference/cdc-class.md) функции-члены.  
  
##  <a name="a-namewillambientsbevalidduringloada--colecontrolwillambientsbevalidduringload"></a><a name="willambientsbevalidduringload"></a>COleControl::WillAmbientsBeValidDuringLoad  
 Определяет, должен ли элемент управления использовать значения свойств окружения как значения по умолчанию, если впоследствии загружается из постоянного состояния.  
  
```  
BOOL WillAmbientsBeValidDuringLoad();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение указывает, что свойства окружения будет допустимым; в противном случае внешние свойства не действительна.  
  
### <a name="remarks"></a>Примечания  
 В некоторых контейнерах, элемент управления может не иметь доступа к свойствам окружения при первом вызове переопределение `COleControl::DoPropExchange`. Это происходит, если контейнер вызывает [IPersistStreamInit::Load](http://msdn.microsoft.com/library/windows/desktop/ms680730) или [IPersistStorage::Load](http://msdn.microsoft.com/library/windows/desktop/ms680557) до вызова метода [IOleObject::SetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms684013) (то есть, если она не учитывает **OLEMISC_SETCLIENTSITEFIRST** бит состояния).  
  
##  <a name="a-namewindowproca--colecontrolwindowproc"></a><a name="windowproc"></a>COleControl::WindowProc  
 Содержит процедуры Windows `COleControl` объекта.  
  
```  
virtual LRESULT WindowProc(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 `message`  
 Указывает сообщение Windows для обработки.  
  
 `wParam`  
 Предоставляет дополнительные сведения, используемые при обработке сообщения. Значение параметра зависит от сообщения.  
  
 `lParam`  
 Предоставляет дополнительные сведения, используемые при обработке сообщения. Значение параметра зависит от сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение отправленных сообщений.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для отправки определенных сообщений через схемы сообщений для элемента управления.  
  
## <a name="see-also"></a>См. также  
 [Образец CIRC3 MFC](../../visual-cpp-samples.md)   
 [Пример MFC TESTHELP](../../visual-cpp-samples.md)   
 [Класс COlePropertyPage](../../mfc/reference/colepropertypage-class.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CFontHolder](../../mfc/reference/cfontholder-class.md)   
 [Класс CPictureHolder](../../mfc/reference/cpictureholder-class.md)

