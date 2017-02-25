---
title: "COleControl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControl class"
  - "элементы управления [MFC], OLE"
  - "элементы управления [MFC], windowless"
  - "элементы управления OLE, MFC - библиотека"
  - "windowless controls"
  - "windowless controls, MFC - библиотека"
ms.assetid: 53e95299-38e8-447b-9c5f-a381d27f5123
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# COleControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Мощный базовый класс для разработки OLE элементы управления.  
  
## Синтаксис  
  
```  
class COleControl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleControl::COleControl](../Topic/COleControl::COleControl.md)|Создает объект `COleControl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleControl::AmbientAppearance](../Topic/COleControl::AmbientAppearance.md)|Извлекает текущий вид элемента управления.|  
|[COleControl::AmbientBackColor](../Topic/COleControl::AmbientBackColor.md)|Возвращает значение внешнего свойства BackColor.|  
|[COleControl::AmbientDisplayName](../Topic/COleControl::AmbientDisplayName.md)|Возвращает имя элемента управления в соответствии с контейнером.|  
|[COleControl::AmbientFont](../Topic/COleControl::AmbientFont.md)|Возвращает значение внешнего свойства шрифта.|  
|[COleControl::AmbientForeColor](../Topic/COleControl::AmbientForeColor.md)|Возвращает значение внешнего свойства ForeColor.|  
|[COleControl::AmbientLocaleID](../Topic/COleControl::AmbientLocaleID.md)|Возвращает идентификатор языкового стандарта контейнера|  
|[COleControl::AmbientScaleUnits](../Topic/COleControl::AmbientScaleUnits.md)|Возвращает тип единиц, используемых контейнером.|  
|[COleControl::AmbientShowGrabHandles](../Topic/COleControl::AmbientShowGrabHandles.md)|Определяет, ручки должны отображаться.|  
|[COleControl::AmbientShowHatching](../Topic/COleControl::AmbientShowHatching.md)|Определяет, штриховкой должен отображаться.|  
|[COleControl::AmbientTextAlign](../Topic/COleControl::AmbientTextAlign.md)|Возвращает тип выравнивания текста указанным контейнером.|  
|[COleControl::AmbientUIDead](../Topic/COleControl::AmbientUIDead.md)|Определяет, если элемент управления должен отвечать на действия интерфейса пользователя.|  
|[COleControl::AmbientUserMode](../Topic/COleControl::AmbientUserMode.md)|Указывает режим контейнера.|  
|[COleControl::BoundPropertyChanged](../Topic/COleControl::BoundPropertyChanged.md)|Уведомляет контейнер, что связанное свойство было изменен.|  
|[COleControl::BoundPropertyRequestEdit](../Topic/COleControl::BoundPropertyRequestEdit.md)|Запрашивает разрешение на изменение значения свойства.|  
|[COleControl::ClientToParent](../Topic/COleControl::ClientToParent.md)|Преобразует точку относительно начала координат элемента управления в точку относительно начала координат его контейнера.|  
|[COleControl::ClipCaretRect](../Topic/COleControl::ClipCaretRect.md)|Обрабатывает прямоугольник курсора, если он перекрывающиеся элементом управления.|  
|[COleControl::ControlInfoChanged](../Topic/COleControl::ControlInfoChanged.md)|Эта функция вызывается после набора мнемоник обращанных элементом управления изменяется.|  
|[COleControl::DisplayError](../Topic/COleControl::DisplayError.md)|События ошибок отображает резервирование пользователю элемента управления.|  
|[COleControl::DoClick](../Topic/COleControl::DoClick.md)|Реализация метода `DoClick` стандартное.|  
|[COleControl::DoPropExchange](../Topic/COleControl::DoPropExchange.md)|Сериализует свойства объекта `COleControl`.|  
|[COleControl::DoSuperclassPaint](../Topic/COleControl::DoSuperclassPaint.md)|Перерисовывает элемент OLE управления, который был subclassed из элемента управления Windows.|  
|[COleControl::EnableSimpleFrame](../Topic/COleControl::EnableSimpleFrame.md)|Содержит простую поддержку фрейма для элемента управления.|  
|[COleControl::ExchangeExtent](../Topic/COleControl::ExchangeExtent.md)|Сериализует ширину и высоту элемента управления.|  
|[COleControl::ExchangeStockProps](../Topic/COleControl::ExchangeStockProps.md)|Сериализует стандартные свойства элемента управления.|  
|[COleControl::ExchangeVersion](../Topic/COleControl::ExchangeVersion.md)|Сериализует номер версии элемента управления.|  
|[COleControl::FireClick](../Topic/COleControl::FireClick.md)|Вызывает событие `Click` стандартное.|  
|[COleControl::FireDblClick](../Topic/COleControl::FireDblClick.md)|Вызывает событие `DblClick` стандартное.|  
|[COleControl::FireError](../Topic/COleControl::FireError.md)|Вызывает событие `Error` стандартное.|  
|[COleControl::FireEvent](../Topic/COleControl::FireEvent.md)|Вызывает пользовательское событие.|  
|[COleControl::FireKeyDown](../Topic/COleControl::FireKeyDown.md)|Вызывает событие `KeyDown` стандартное.|  
|[COleControl::FireKeyPress](../Topic/COleControl::FireKeyPress.md)|Вызывает событие `KeyPress` стандартное.|  
|[COleControl::FireKeyUp](../Topic/COleControl::FireKeyUp.md)|Вызывает событие `KeyUp` стандартное.|  
|[COleControl::FireMouseDown](../Topic/COleControl::FireMouseDown.md)|Вызывает событие `MouseDown` стандартное.|  
|[COleControl::FireMouseMove](../Topic/COleControl::FireMouseMove.md)|Вызывает событие `MouseMove` стандартное.|  
|[COleControl::FireMouseUp](../Topic/COleControl::FireMouseUp.md)|Вызывает событие `MouseUp` стандартное.|  
|[COleControl::FireReadyStateChange](../Topic/COleControl::FireReadyStateChange.md)|Вызывает событие при изменении состояния готово элемента управления.|  
|[COleControl::GetActivationPolicy](../Topic/COleControl::GetActivationPolicy.md)|Изменяет по умолчанию расширения функциональности активации элемента управления, поддерживающего интерфейс `IPointerInactive`.|  
|[COleControl::GetAmbientProperty](../Topic/COleControl::GetAmbientProperty.md)|Возвращает значение указанного внешнего свойства.|  
|[COleControl::GetAppearance](../Topic/COleControl::GetAppearance.md)|Возвращает значение свойства внешнего вида стандартное.|  
|[COleControl::GetBackColor](../Topic/COleControl::GetBackColor.md)|Возвращает значение свойства BackColor стандартное.|  
|[COleControl::GetBorderStyle](../Topic/COleControl::GetBorderStyle.md)|Возвращает значение свойства BorderStyle стандартное.|  
|[COleControl::GetCapture](../Topic/COleControl::GetCapture.md)|Определяет, имеет ли безоконный, активированный объект элемента управления захват мыши.|  
|[COleControl::GetClassID](../Topic/COleControl::GetClassID.md)|Извлекает OLE идентификатор класса элемента управления.|  
|[COleControl::GetClientOffset](../Topic/COleControl::GetClientOffset.md)|Возвращает разницу между верхним левым углом прямоугольной области элемента управления и верхним левым углом клиентской области.|  
|[COleControl::GetClientRect](../Topic/COleControl::GetClientRect.md)|Возвращает размер клиентской области элемента управления.|  
|[COleControl::GetClientSite](../Topic/COleControl::GetClientSite.md)|Запрашивает объект для указателя на свой текущий сайту клиента в пределах своего контейнера.|  
|[COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md)|Возвращает параметры пометить элемента управления.|  
|[COleControl::GetControlSize](../Topic/COleControl::GetControlSize.md)|Возвращает расположение и размер элемента управления OLE.|  
|[COleControl::GetDC](../Topic/COleControl::GetDC.md)|Предоставляет середины для безоконного элемента управления получить контекст устройства из своего контейнера.|  
|[COleControl::GetEnabled](../Topic/COleControl::GetEnabled.md)|Возвращает значение свойства включено запасом.|  
|[COleControl::GetExtendedControl](../Topic/COleControl::GetExtendedControl.md)|Извлекает указатель на объект выдвинутому управления, принадлежащие к контейнеру.|  
|[COleControl::GetFocus](../Topic/COleControl::GetFocus.md)|Указывает, установлен ли на элементе управления фокус.|  
|[COleControl::GetFont](../Topic/COleControl::GetFont.md)|Возвращает значение свойства шрифта стандартное.|  
|[COleControl::GetFontTextMetrics](../Topic/COleControl::GetFontTextMetrics.md)|Возвращает метрики объекта `CFontHolder`.|  
|[COleControl::GetForeColor](../Topic/COleControl::GetForeColor.md)|Возвращает значение свойства ForeColor стандартное.|  
|[COleControl::GetHwnd](../Topic/COleControl::GetHwnd.md)|Возвращает значение свойства hWnd стандартное.|  
|[COleControl::GetMessageString](../Topic/COleControl::GetMessageString.md)|Содержит текст строки состояния для пункта меню.|  
|[COleControl::GetNotSupported](../Topic/COleControl::GetNotSupported.md)|Предотвращает доступ к значению свойства элемента управления пользователем.|  
|[COleControl::GetReadyState](../Topic/COleControl::GetReadyState.md)|Возвращает состояние готовности к элемента управления.|  
|[COleControl::GetRectInContainer](../Topic/COleControl::GetRectInContainer.md)|Возвращает прямоугольник для элемента управления относительно его контейнер.|  
|[COleControl::GetStockTextMetrics](../Topic/COleControl::GetStockTextMetrics.md)|Возвращает метрики свойства шрифта стандартное.|  
|[COleControl::GetText](../Topic/COleControl::GetText.md)|Возвращает значение свойства текста или заголовка стандартное.|  
|[COleControl::GetWindowlessDropTarget](../Topic/COleControl::GetWindowlessDropTarget.md)|Переопределение для разрешения безоконный элемент управления, чтобы быть целевым объектом перетаскивания и удаление операций.|  
|[COleControl::InitializeIIDs](../Topic/COleControl::InitializeIIDs.md)|Предоставляет базовый класс IIDs элемент управления будет использоваться.|  
|[COleControl::InternalGetFont](../Topic/COleControl::InternalGetFont.md)|Возвращает объект `CFontHolder` для стандартных свойств шрифта.|  
|[COleControl::InternalGetText](../Topic/COleControl::InternalGetText.md)|Извлекает свойство заголовка и тела стандартное.|  
|[COleControl::InternalSetReadyState](../Topic/COleControl::InternalSetReadyState.md)|Устанавливает состояние готовности к элемента управления и вызывает событие готов\-состояние\- изменения.|  
|[COleControl::InvalidateControl](../Topic/COleControl::InvalidateControl.md)|Делает недействительной область элемента управления, отображаемого, поэтому она перерисовать.|  
|[COleControl::InvalidateRgn](../Topic/COleControl::InvalidateRgn.md)|Делает недействительной клиентская область окна контейнера в заданной области.  Может использоваться для перерисовывать безоконные элементы управления в область.|  
|[COleControl::IsConvertingVBX](../Topic/COleControl::IsConvertingVBX.md)|Разрешает OLE специализировало загрузку элемента управления.|  
|[COleControl::IsModified](../Topic/COleControl::IsModified.md)|Определяет, если состояние элемента управления изменилось.|  
|[COleControl::IsOptimizedDraw](../Topic/COleControl::IsOptimizedDraw.md)|Указывает, поддерживает ли контейнер оптимизированного документ для текущей операции рисования.|  
|[COleControl::IsSubclassedControl](../Topic/COleControl::IsSubclassedControl.md)|Вызванный, чтобы определить, что подклассы элемента управления Windows.|  
|[COleControl::Load](../Topic/COleControl::Load.md)|Сбросить все предыдущие асинхронные данные и начинает новую загрузку свойств элемента управления асинхронной.|  
|[COleControl::LockInPlaceActive](../Topic/COleControl::LockInPlaceActive.md)|Определяет, если элемент управления может быть отключен контейнером.|  
|[COleControl::OnAmbientPropertyChange](../Topic/COleControl::OnAmbientPropertyChange.md)|Вызываемый при изменен внешнее свойство.|  
|[COleControl::OnAppearanceChanged](../Topic/COleControl::OnAppearanceChanged.md)|Вызываемый при изменен стандартное свойство вид.|  
|[COleControl::OnBackColorChanged](../Topic/COleControl::OnBackColorChanged.md)|Если свойству BackColor с именем биржевых изменен.|  
|[COleControl::OnBorderStyleChanged](../Topic/COleControl::OnBorderStyleChanged.md)|Вызываемый, когда свойства BorderStyle акций изменен.|  
|[COleControl::OnClick](../Topic/COleControl::OnClick.md)|Вызванный, чтобы создать событие click стандартное.|  
|[COleControl::OnClose](../Topic/COleControl::OnClose.md)|Уведомляет элемент управления, что `IOleControl::Close` было вызываются.|  
|[COleControl::OnDoVerb](../Topic/COleControl::OnDoVerb.md)|Вызываемый после того как команда элемента управления была исполнена.|  
|[COleControl::OnDraw](../Topic/COleControl::OnDraw.md)|Вызываемый, когда поставлена о необходимости перерисовки элемента управления.|  
|[COleControl::OnDrawMetafile](../Topic/COleControl::OnDrawMetafile.md)|Вызванный контейнером при будет предложено о необходимости перерисовки элемента управления, используя контекст устройства метафайла.|  
|[COleControl::OnEdit](../Topic/COleControl::OnEdit.md)|Активировать размещенные с контейнером для пользовательского интерфейса OLE элемент управления.|  
|[COleControl::OnEnabledChanged](../Topic/COleControl::OnEnabledChanged.md)|Если свойство включено изменен с запасом.|  
|[COleControl::OnEnumVerbs](../Topic/COleControl::OnEnumVerbs.md)|Вызванный контейнером для перечисления команды элемента управления.|  
|[COleControl::OnEventAdvise](../Topic/COleControl::OnEventAdvise.md)|Вызываемый при подключены обработчики событий или отключен от элемента управления.|  
|[COleControl::OnFontChanged](../Topic/COleControl::OnFontChanged.md)|Вызываемый при изменен стандартное свойство шрифта.|  
|[COleControl::OnForeColorChanged](../Topic/COleControl::OnForeColorChanged.md)|Если для свойства ForeColor акций с именем изменен.|  
|[COleControl::OnFreezeEvents](../Topic/COleControl::OnFreezeEvents.md)|Вызываемый при заморозитьы или unfrozen события элемента управления.|  
|[COleControl::OnGetColorSet](../Topic/COleControl::OnGetColorSet.md)|Уведомляет элемент управления, что `IOleObject::GetColorSet` было вызываются.|  
|[COleControl::OnGetControlInfo](../Topic/COleControl::OnGetControlInfo.md)|Предоставляет сведения mnemonic контейнер.|  
|[COleControl::OnGetDisplayString](../Topic/COleControl::OnGetDisplayString.md)|Вызываемый для получения строки для представления значения свойства.|  
|[COleControl::OnGetInPlaceMenu](../Topic/COleControl::OnGetInPlaceMenu.md)|Запрашивает маркер меню элемента управления, которое будет объединитьо с меню контейнера.|  
|[COleControl::OnGetNaturalExtent](../Topic/COleControl::OnGetNaturalExtent.md)|Переопределение для получения размер отображения элемента управления, ближайший к предложенному режим изменения размера and extents.|  
|[COleControl::OnGetPredefinedStrings](../Topic/COleControl::OnGetPredefinedStrings.md)|Возвращает шнуруют представляющие возможные значения для свойства.|  
|[COleControl::OnGetPredefinedValue](../Topic/COleControl::OnGetPredefinedValue.md)|Возвращает значение, соответствующее предопределенной строке.|  
|[COleControl::OnGetViewExtent](../Topic/COleControl::OnGetViewExtent.md)|Переопределение для получения размер областей отображения элемента управления \(могут использоваться для включения двух траекторный документ\).|  
|[COleControl::OnGetViewRect](../Topic/COleControl::OnGetViewRect.md)|Переопределение для преобразования размер элемента управления в прямоугольник, начиная с указанной позиции.|  
|[COleControl::OnGetViewStatus](../Topic/COleControl::OnGetViewStatus.md)|Переопределение для восстановления состояния представления элемента управления.|  
|[COleControl::OnHideToolBars](../Topic/COleControl::OnHideToolBars.md)|Вызванный контейнером при выключенный элемент управления пользовательского интерфейса.|  
|[COleControl::OnInactiveMouseMove](../Topic/COleControl::OnInactiveMouseMove.md)|Переопределение иметь контейнер для неактивного элемента управления с сообщениями `WM_MOUSEMOVE` диспетчера указателя мыши на элемент управления.|  
|[COleControl::OnInactiveSetCursor](../Topic/COleControl::OnInactiveSetCursor.md)|Переопределение иметь контейнер для неактивного элемента управления с сообщениями `WM_SETCURSOR` диспетчера указателя мыши на элемент управления.|  
|[COleControl::OnKeyDownEvent](../Topic/COleControl::OnKeyDownEvent.md)|Вызываемый после события KeyDown резервирование было инициировано.|  
|[COleControl::OnKeyPressEvent](../Topic/COleControl::OnKeyPressEvent.md)|Вызываемый после события KeyPress резервирование было инициировано.|  
|[COleControl::OnKeyUpEvent](../Topic/COleControl::OnKeyUpEvent.md)|Вызываемый после того, как событие KeyUp резервирование было инициировано.|  
|[COleControl::OnMapPropertyToPage](../Topic/COleControl::OnMapPropertyToPage.md)|Указывает, страница свойств, используемый для редактирования свойства.|  
|[COleControl::OnMnemonic](../Topic/COleControl::OnMnemonic.md)|Вызываемый, когда был нажат mnemonic ключ элемента управления.|  
|[COleControl::OnProperties](../Topic/COleControl::OnProperties.md)|Вызываемый, когда вызвана команда "свойства" элемента управления.|  
|[COleControl::OnQueryHitPoint](../Topic/COleControl::OnQueryHitPoint.md)|Переопределение для запроса, перекрывается ли отображение элемента управления заданную точку.|  
|[COleControl::OnQueryHitRect](../Topic/COleControl::OnQueryHitRect.md)|Переопределение для запроса, перекрывается ли отображение элемента управления любую точку в заданном прямоугольнике.|  
|[COleControl::OnRenderData](../Topic/COleControl::OnRenderData.md)|Вызываемый платформой для получения данных в указанном формате.|  
|[COleControl::OnRenderFileData](../Topic/COleControl::OnRenderFileData.md)|Вызываемый платформой для извлечения данных из файлов в указанном формате.|  
|[COleControl::OnRenderGlobalData](../Topic/COleControl::OnRenderGlobalData.md)|Вызываемый платформой для получения данных из глобальной памяти в указанном формате.|  
|[COleControl::OnResetState](../Topic/COleControl::OnResetState.md)|Сбросить свойства элемента управления значения по умолчанию.|  
|[COleControl::OnSetClientSite](../Topic/COleControl::OnSetClientSite.md)|Уведомляет элемент управления, что `IOleControl::SetClientSite` было вызываются.|  
|[COleControl::OnSetData](../Topic/COleControl::OnSetData.md)|Заменяет контрольна данные с другим значением.|  
|[COleControl::OnSetExtent](../Topic/COleControl::OnSetExtent.md)|Вызываемый после области элемента управления изменяется.|  
|[COleControl::OnSetObjectRects](../Topic/COleControl::OnSetObjectRects.md)|Вызываемый после того, как были изменены размеры элемента управления.|  
|[COleControl::OnShowToolBars](../Topic/COleControl::OnShowToolBars.md)|Вызываемый, когда элемент управления активированный пользовательский интерфейс.|  
|[COleControl::OnTextChanged](../Topic/COleControl::OnTextChanged.md)|Вызываемый при изменен свойство текста или заголовка стандартное.|  
|[COleControl::OnWindowlessMessage](../Topic/COleControl::OnWindowlessMessage.md)|Сообщения окна процессов \(за исключением сообщений мыши и клавиатуры\) для безоконных элементов управления.|  
|[COleControl::ParentToClient](../Topic/COleControl::ParentToClient.md)|Преобразует точку относительно начала координат контейнера до точки относительно начала координат элемента управления.|  
|[COleControl::PostModalDialog](../Topic/COleControl::PostModalDialog.md)|Уведомляет контейнер, что модальное диалоговое окно было закрыто.|  
|[COleControl::PreModalDialog](../Topic/COleControl::PreModalDialog.md)|Уведомляет контейнер, что модальное диалоговое окно будет отображаться.|  
|[COleControl::RecreateControlWindow](../Topic/COleControl::RecreateControlWindow.md)|Удаляет и воссоздает окно элемента управления.|  
|[COleControl::Refresh](../Topic/COleControl::Refresh.md)|Вызывает принудительное обновление внешнего вида элемента управления.|  
|[COleControl::ReleaseCapture](../Topic/COleControl::ReleaseCapture.md)|Захват мыши выпусков.|  
|[COleControl::ReleaseDC](../Topic/COleControl::ReleaseDC.md)|Освобождает дисплейного контекст устройства контейнера безоконного элемента управления.|  
|[COleControl::ReparentControlWindow](../Topic/COleControl::ReparentControlWindow.md)|Сбросить родительского окна элемента управления.|  
|[COleControl::ResetStockProps](../Topic/COleControl::ResetStockProps.md)|Инициализирует `COleControl` стандартные свойства с их значениями по умолчанию.|  
|[COleControl::ResetVersion](../Topic/COleControl::ResetVersion.md)|Инициализирует номер версии на заданное значение.|  
|[COleControl::ScrollWindow](../Topic/COleControl::ScrollWindow.md)|Позволяет безоконный элемент управления прокрутку область в пределах своего завершения образа в\- размещения активного на экране.|  
|[COleControl::SelectFontObject](../Topic/COleControl::SelectFontObject.md)|Выберите свойство пользовательского шрифта в контекст устройства.|  
|[COleControl::SelectStockFont](../Topic/COleControl::SelectStockFont.md)|Выберите свойство шрифта акций в контекст устройства.|  
|[COleControl::SerializeExtent](../Topic/COleControl::SerializeExtent.md)|Сериализует или инициализирует место отображения для элемента управления.|  
|[COleControl::SerializeStockProps](../Topic/COleControl::SerializeStockProps.md)|Сериализует или инициализирует `COleControl` стандартные свойства.|  
|[COleControl::SerializeVersion](../Topic/COleControl::SerializeVersion.md)|Сериализует или инициализирует сведения о версии элемента управления.|  
|[COleControl::SetAppearance](../Topic/COleControl::SetAppearance.md)|Присваивает значение свойства внешнего вида стандартное.|  
|[COleControl::SetBackColor](../Topic/COleControl::SetBackColor.md)|Присваивает значение свойства BackColor стандартное.|  
|[COleControl::SetBorderStyle](../Topic/COleControl::SetBorderStyle.md)|Присваивает значение свойства BorderStyle стандартное.|  
|[COleControl::SetCapture](../Topic/COleControl::SetCapture.md)|Вызывает окно контейнера элемента управления стать владельцем захвата мыши на имени элемента управления.|  
|[COleControl::SetControlSize](../Topic/COleControl::SetControlSize.md)|Задает положение и размер элемента управления OLE.|  
|[COleControl::SetEnabled](../Topic/COleControl::SetEnabled.md)|Присваивает значение свойства включено запасом.|  
|[COleControl::SetFocus](../Topic/COleControl::SetFocus.md)|Вызывает окно контейнера элемента управления стать владельцем фокуса ввода от имени элемента управления.|  
|[COleControl::SetFont](../Topic/COleControl::SetFont.md)|Присваивает значение свойства шрифта стандартное.|  
|[COleControl::SetForeColor](../Topic/COleControl::SetForeColor.md)|Присваивает значение свойства ForeColor стандартное.|  
|[COleControl::SetInitialSize](../Topic/COleControl::SetInitialSize.md)|Задает размер элемента управления при первом OLE, показанный в контейнере.|  
|[COleControl::SetModifiedFlag](../Topic/COleControl::SetModifiedFlag.md)|Изменяет измененное состояние элемента управления.|  
|[COleControl::SetNotPermitted](../Topic/COleControl::SetNotPermitted.md)|Указывает, что запрос правки терпел ошибкой.|  
|[COleControl::SetNotSupported](../Topic/COleControl::SetNotSupported.md)|Предотвращает изменение свойства элемента управления пользователем.|  
|[COleControl::SetRectInContainer](../Topic/COleControl::SetRectInContainer.md)|Задает прямоугольник элемента управления относительно его контейнер.|  
|[COleControl::SetText](../Topic/COleControl::SetText.md)|Присваивает значение свойства текста или заголовка стандартное.|  
|[COleControl::ThrowError](../Topic/COleControl::ThrowError.md)|Сообщает, что произошла ошибка OLE в элементе управления.|  
|[COleControl::TransformCoords](../Topic/COleControl::TransformCoords.md)|Преобразовывает значения координат между контейнером и элементом управления.|  
|[COleControl::TranslateColor](../Topic/COleControl::TranslateColor.md)|Преобразует значение в значение **OLE\_COLORCOLORREF**.|  
|[COleControl::WillAmbientsBeValidDuringLoad](../Topic/COleControl::WillAmbientsBeValidDuringLoad.md)|Определяет, будут ли внешние свойства доступны при следующем запуске элемента управления будут загружаться.|  
|[COleControl::WindowProc](../Topic/COleControl::WindowProc.md)|Предоставляет процедуру Windows для объекта `COleControl`.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleControl::DrawContent](../Topic/COleControl::DrawContent.md)|Вызываемый платформой, если представление элемента управления необходимо обновить.|  
|[COleControl::DrawMetafile](../Topic/COleControl::DrawMetafile.md)|Вызываемый платформой, если используется контекст устройства метафайла.|  
|[COleControl::IsInvokeAllowed](../Topic/COleControl::IsInvokeAllowed.md)|Включает вызов метода автоматизации.|  
|[COleControl::SetInitialDataFormats](../Topic/COleControl::SetInitialDataFormats.md)|Вызываемый платформой для инициализации список форматов данных, поддерживаемых элементом управления.|  
  
## Заметки  
 Производный от `CWnd` этот класс наследуется всеми функциональными возможностями объектов окна Windows, а также дополнительные функциональные возможности, специфичные для OLE, таких как включение событий и возможность поддерживать методы и свойства.  
  
 OLE элементы управления можно вставить в приложение OLE\-контейнер и взаимодействия с контейнером с помощью системы включения двусторонней событий и методов и свойств в контейнер.  Обратите внимание, что стандартные OLE\-контейнер поддерживают только базовую функциональность OLE элемента управления.  Они не могут поддерживать расширенные функции OLE элемента управления.  Включение событий возникает, когда события отправлены к контейнеру в результате некоторых действий, осуществляя в элементе управления.  В свою очередь, контейнер взаимодействует с элементом управления с помощью набора методов и свойств, предоставляемого аналогичные в функции\-членам и элементам данных C\+\+ классифицируют.  Такой подход позволяет разработчику управлять внешний вид элемента управления и уведомления контейнер, когда некоторые действия.  
  
## Безоконные элементы управления  
 OLE элементы управления могут использоваться отдельно активным в\- размещения без окна.  Безоконные элементы управления имеют значительные преимущества:  
  
-   Безоконные элементы управления могут быть прозрачным и подписчиков, отличных от прямоугольны  
  
-   Безоконные элементы управления уменьшают размер экземпляра и время создания объекта.  
  
 Элементы управления не требуется.  Службы, окно предлагает можно легко обеспечить через одно общее окна \(обычно контейнер\) и бит распределения кода.  Иметь окно в основном лишнее усложнение на объект.  
  
 При безоконная активация используется, контейнер \(который имеет окно отвечает за обеспечение службы\), в противном случае были бы предоставлены собственным окна элемента управления.  Например, если требуется элемента управления запросить фокус клавиатуры, запросить захват мыши или получить контекст устройства, эти операции управляются контейнером.  `COleControl`[функции\-члены безоконный\-операции](http://msdn.microsoft.com/ru-ru/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) вызывает эти операции в контейнере.  
  
 При безоконная активация разрешена, сообщения ввода делегатов контейнера в `IOleInPlaceObjectWindowless` элемента управления, взаимодействующих \(расширения [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) для поддержки безоконной\).  Реализация этого интерфейса `COleControl` пошлет эти сообщения через сопоставление сообщения элемента управления, после обработки координаты мыши.  Можно обрабатывать эти сообщения как обычные сообщения окна, добавив соответствующие записи для сопоставления сообщений.  
  
 В безоконном элементе управления, необходимо всегда использовать функции\-члены `COleControl` вместо соответствующие функции\-члены `CWnd` или их связанных функций API Windows.  
  
 Объекты OLE управления могут также создать окно, только когда они стали активными, но объем работ, необходимые для перехода Неактивен\- проходит активный скорость перехода становится вверх и вниз.  Случаи, когда это проблема: в качестве примера рассмотрим сетку текстовых полей.  Cursoring вверх и вниз по столбцу, каждый элемент управления должен быть затем выключенным в\- размещение и активированным.  Скорость перехода неактивного\/активного непосредственно влияет на скорость прокрутки.  
  
 Дополнительные сведения о разработке OLE границы элемента управления см. в разделе статьи [Элементы управления ActiveX MFC](../../mfc/mfc-activex-controls.md) и [Общие сведения: Создание программы элемент управления ActiveX MFC](../../mfc/reference/mfc-activex-control-wizard.md).  Дополнительные сведения о оптимизировать OLE элементов управления, в том числе управления безоконных и фликер\- свободна см. в разделе [Элементы управления ActiveX MFC: оптимизация](../../mfc/mfc-activex-controls-optimization.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `COleControl`  
  
## Требования  
 **Header:**  afxctl.h  
  
## См. также  
 [MFC просматривает CIRC3](../../top/visual-cpp-samples.md)   
 [Образец TESTHELP MFC](../../top/visual-cpp-samples.md)   
 [COlePropertyPage Class](../../mfc/reference/colepropertypage-class.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFontHolder Class](../../mfc/reference/cfontholder-class.md)   
 [CPictureHolder Class](../../mfc/reference/cpictureholder-class.md)