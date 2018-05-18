---
title: CToolTipCtrl-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CToolTipCtrl
- AFXCMN/CToolTipCtrl
- AFXCMN/CToolTipCtrl::CToolTipCtrl
- AFXCMN/CToolTipCtrl::Activate
- AFXCMN/CToolTipCtrl::AddTool
- AFXCMN/CToolTipCtrl::AdjustRect
- AFXCMN/CToolTipCtrl::Create
- AFXCMN/CToolTipCtrl::CreateEx
- AFXCMN/CToolTipCtrl::DelTool
- AFXCMN/CToolTipCtrl::GetBubbleSize
- AFXCMN/CToolTipCtrl::GetCurrentTool
- AFXCMN/CToolTipCtrl::GetDelayTime
- AFXCMN/CToolTipCtrl::GetMargin
- AFXCMN/CToolTipCtrl::GetMaxTipWidth
- AFXCMN/CToolTipCtrl::GetText
- AFXCMN/CToolTipCtrl::GetTipBkColor
- AFXCMN/CToolTipCtrl::GetTipTextColor
- AFXCMN/CToolTipCtrl::GetTitle
- AFXCMN/CToolTipCtrl::GetToolCount
- AFXCMN/CToolTipCtrl::GetToolInfo
- AFXCMN/CToolTipCtrl::HitTest
- AFXCMN/CToolTipCtrl::Pop
- AFXCMN/CToolTipCtrl::Popup
- AFXCMN/CToolTipCtrl::RelayEvent
- AFXCMN/CToolTipCtrl::SetDelayTime
- AFXCMN/CToolTipCtrl::SetMargin
- AFXCMN/CToolTipCtrl::SetMaxTipWidth
- AFXCMN/CToolTipCtrl::SetTipBkColor
- AFXCMN/CToolTipCtrl::SetTipTextColor
- AFXCMN/CToolTipCtrl::SetTitle
- AFXCMN/CToolTipCtrl::SetToolInfo
- AFXCMN/CToolTipCtrl::SetToolRect
- AFXCMN/CToolTipCtrl::SetWindowTheme
- AFXCMN/CToolTipCtrl::Update
- AFXCMN/CToolTipCtrl::UpdateTipText
dev_langs:
- C++
helpviewer_keywords:
- CToolTipCtrl [MFC], CToolTipCtrl
- CToolTipCtrl [MFC], Activate
- CToolTipCtrl [MFC], AddTool
- CToolTipCtrl [MFC], AdjustRect
- CToolTipCtrl [MFC], Create
- CToolTipCtrl [MFC], CreateEx
- CToolTipCtrl [MFC], DelTool
- CToolTipCtrl [MFC], GetBubbleSize
- CToolTipCtrl [MFC], GetCurrentTool
- CToolTipCtrl [MFC], GetDelayTime
- CToolTipCtrl [MFC], GetMargin
- CToolTipCtrl [MFC], GetMaxTipWidth
- CToolTipCtrl [MFC], GetText
- CToolTipCtrl [MFC], GetTipBkColor
- CToolTipCtrl [MFC], GetTipTextColor
- CToolTipCtrl [MFC], GetTitle
- CToolTipCtrl [MFC], GetToolCount
- CToolTipCtrl [MFC], GetToolInfo
- CToolTipCtrl [MFC], HitTest
- CToolTipCtrl [MFC], Pop
- CToolTipCtrl [MFC], Popup
- CToolTipCtrl [MFC], RelayEvent
- CToolTipCtrl [MFC], SetDelayTime
- CToolTipCtrl [MFC], SetMargin
- CToolTipCtrl [MFC], SetMaxTipWidth
- CToolTipCtrl [MFC], SetTipBkColor
- CToolTipCtrl [MFC], SetTipTextColor
- CToolTipCtrl [MFC], SetTitle
- CToolTipCtrl [MFC], SetToolInfo
- CToolTipCtrl [MFC], SetToolRect
- CToolTipCtrl [MFC], SetWindowTheme
- CToolTipCtrl [MFC], Update
- CToolTipCtrl [MFC], UpdateTipText
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de230a82adaaafc149d2ed5a762977205c798b03
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl Class
Инкапсулирует функциональность элемента управления "всплывающая подсказка" — небольшого всплывающего окна, в котором отображается одна строка текста, описывающая назначение инструмента в приложении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CToolTipCtrl::CToolTipCtrl](#ctooltipctrl)|Создает объект `CToolTipCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CToolTipCtrl::Activate](#activate)|Активирует и деактивирует всплывающая подсказка.|  
|[CToolTipCtrl::AddTool](#addtool)|Регистрирует это средство управления всплывающей подсказки.|  
|[CToolTipCtrl::AdjustRect](#adjustrect)|Преобразует между текст элемента управления всплывающей подсказки на отображение прямоугольник и его окно прямоугольник.|  
|[CToolTipCtrl::Create](#create)|Создание элемента управления всплывающей подсказки и прикрепляет его к `CToolTipCtrl` объекта.|  
|[CToolTipCtrl::CreateEx](#createex)|Создает элемента управления всплывающей подсказки с указанным расширенные стили Windows и прикрепляет его к `CToolTipCtrl` объекта.|  
|[CToolTipCtrl::DelTool](#deltool)|Удаляет из управления всплывающей подсказки.|  
|[CToolTipCtrl::GetBubbleSize](#getbubblesize)|Получает размер всплывающей подсказки.|  
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|Получает сведения, такие как размер, положение и текст окна всплывающей подсказки, отображающий текущего элемента управления всплывающей подсказки.|  
|[CToolTipCtrl::GetDelayTime](#getdelaytime)|Получает начальное, всплывающее окно и reshow длительности, заданных для средства в настоящее время элемента управления подсказки.|  
|[CToolTipCtrl::GetMargin](#getmargin)|Получает начало, левую, нижнюю и правого полей, заданных для подсказки.|  
|[CToolTipCtrl::GetMaxTipWidth](#getmaxtipwidth)|Возвращает максимальную ширину для подсказки.|  
|[CToolTipCtrl::GetText](#gettext)|Извлекает текст, который поддерживает всплывающая подсказка для средства.|  
|[CToolTipCtrl::GetTipBkColor](#gettipbkcolor)|Возвращает цвет фона в окне инструментов подсказки.|  
|[CToolTipCtrl::GetTipTextColor](#gettiptextcolor)|Возвращает цвет текста в окне инструментов подсказки.|  
|[CToolTipCtrl::GetTitle](#gettitle)|Возвращает название текущего элемента управления всплывающей подсказки.|  
|[CToolTipCtrl::GetToolCount](#gettoolcount)|Извлекает количество средств, поддерживаемых элементом управления всплывающей подсказки.|  
|[CToolTipCtrl::GetToolInfo](#gettoolinfo)|Извлекает сведения о средстве, обслуживает всплывающая подсказка.|  
|[CToolTipCtrl::HitTest](#hittest)|Проверяет точку, чтобы определить, является ли оно внутри ограничивающего прямоугольника данное средство. В этом случае извлекает информацию об этом инструменте.|  
|[CToolTipCtrl::Pop](#pop)|Удаляет отображаемые подсказки из представления.|  
|[CToolTipCtrl::Popup](#popup)|Вызывает текущего элемента управления всплывающей подсказки для отображения в координатах последнее сообщение мыши.|  
|[CToolTipCtrl::RelayEvent](#relayevent)|Передает сообщение мыши элементом управления всплывающей подсказки для обработки.|  
|[CToolTipCtrl::SetDelayTime](#setdelaytime)|Задает исходное всплывающего окна и reshow длительности для элемента управления всплывающей подсказки.|  
|[CToolTipCtrl::SetMargin](#setmargin)|Задает начало, левую, нижнюю и правого полей для подсказки.|  
|[CToolTipCtrl::SetMaxTipWidth](#setmaxtipwidth)|Задает максимальную ширину для подсказки.|  
|[CToolTipCtrl::SetTipBkColor](#settipbkcolor)|Задает цвет фона в окне инструментов подсказки.|  
|[CToolTipCtrl::SetTipTextColor](#settiptextcolor)|Задает цвет текста в окне инструментов подсказки.|  
|[CToolTipCtrl::SetTitle](#settitle)|Добавляет стандартную строку, значок и заголовок подсказки.|  
|[CToolTipCtrl::SetToolInfo](#settoolinfo)|Задает сведения, которые поддерживает во всплывающей подсказке инструмента.|  
|[CToolTipCtrl::SetToolRect](#settoolrect)|Задает ограничивающий прямоугольник для средства.|  
|[CToolTipCtrl::SetWindowTheme](#setwindowtheme)|Задает визуальный стиль подсказки.|  
|[CToolTipCtrl::Update](#update)|Вызывает перерисовку текущего инструмента.|  
|[CToolTipCtrl::UpdateTipText](#updatetiptext)|Задает текст подсказки для средства.|  
  
## <a name="remarks"></a>Примечания  
 «Средство» — либо это окно, такие как дочернего окна элемента управления или определяемые приложением прямоугольная область в клиентской области окна. Во всплывающей подсказке скрыто в большинстве случаев, появляющихся только когда пользователь помещает курсор над инструментом и оставляет его на примерно половину второй. Подсказка появляется рядом с курсором и исчезает, когда пользователь нажимает кнопку мыши или перемещает курсор средство.  
  
 `CToolTipCtrl` предоставляет функциональные возможности для управления начальное время и длительность всплывающей подсказки, ширина полей, окружающих текст подсказки, ширина подсказки сам и цвета фона и текста всплывающей подсказки. Всплывающая подсказка одного могут предоставить сведения для более чем одного набора инструментов.  
  
 `CToolTipCtrl` Класс предоставляет функциональные возможности элемента управления Windows общих всплывающая подсказка. Этот элемент управления (и, следовательно, `CToolTipCtrl` класс) доступен только для программ, под управлением версий Windows 95/98 и Windows NT 3.51 и более поздних.  
  
 Дополнительные сведения о включении всплывающие подсказки см. в разделе [всплывающие подсказки в Windows не являющиеся производными CFrameWnd](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
 Дополнительные сведения об использовании `CToolTipCtrl`, в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CToolTipCtrl](../../mfc/using-ctooltipctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolTipCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="activate"></a>  CToolTipCtrl::Activate  
 Вызывайте эту функцию, чтобы активировать или деактивировать всплывающая подсказка.  
  
```  
void Activate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 `bActivate`  
 Указывает, является ли всплывающая подсказка для активации или деактивации.  
  
### <a name="remarks"></a>Примечания  
 Если `bActivate` — **TRUE**, активации элемента управления; Если **FALSE**, он отключен.  
  
 При активном всплывающая подсказка средство сведения подсказки отображается при прохождении курсора над инструментом, который регистрируется с помощью элемента управления; Если неактивен, средство совет сведения не отображается, даже если курсор находится над инструментом.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="addtool"></a>  CToolTipCtrl::AddTool  
 Регистрирует это средство управления всплывающей подсказки.  
  
```  
BOOL AddTool(
    CWnd* pWnd,  
    UINT nIDText,  
    LPCRECT lpRectTool = NULL,  
    UINT_PTR nIDTool = 0);

 
BOOL AddTool(
    CWnd* pWnd,  
    LPCTSTR lpszText = LPSTR_TEXTCALLBACK,  
    LPCRECT lpRectTool = NULL,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, содержащей это средство.  
  
 `nIDText`  
 Идентификатор строкового ресурса, содержащий текст для средства.  
  
 *lpRectTool*  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, содержащую средство координаты ограничивающего прямоугольника. Координаты указываются относительно левого верхнего угла клиентской области окна, обозначенную `pWnd`.  
  
 `nIDTool`  
 Идентификатор средства.  
  
 `lpszText`  
 Указатель на текст для средства. Если этот параметр содержит значение **LPSTR_TEXTCALLBACK**, **TTN_NEEDTEXT** сообщений уведомления перейти к родительского окна, `pWnd` указывает.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 **LpRectTool** и **nIDTool** параметров должны быть допустимыми, либо если **lpRectTool** имеет значение NULL, **nIDTool** должно быть равно 0.  
  
 Всплывающая подсказка может быть связан более чем одного набора инструментов. Эта функция вызывается для регистрации средство управления всплывающей подсказки для отображения сведений, хранящихся в подсказке, когда курсор находится в средстве.  
  
> [!NOTE]
>  Невозможно задать всплывающую подсказку в статический элемент управления с помощью `AddTool`.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="adjustrect"></a>  CToolTipCtrl::AdjustRect  
 Преобразует между текст всплывающей подсказки элемента управления отображения прямоугольник и его окно прямоугольник.  
  
```  
BOOL AdjustRect(
    LPRECT lprc,  
    BOOL bLarger = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `lprc`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, которая содержит прямоугольник окно подсказки средство или прямоугольник отображаемого текста.  
  
 `bLarger`  
 Если **TRUE**, `lprc` используется для указания прямоугольник отображения текста и получает соответствующие прямоугольника окна. Если **FALSE**, `lprc` используется для указания прямоугольник окна, и он получает соответствующий прямоугольник отображения текста.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если прямоугольник успешно изменены; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вычисляет прямоугольник отображения текста элемента управления всплывающей подсказки элемента из его окно прямоугольника или прямоугольника окна совет средство, необходимые для отображения прямоугольник отображения указанного текста.  
  
 Эта функция-член реализует поведение сообщения Win32 [TTM_ADJUSTRECT](http://msdn.microsoft.com/library/windows/desktop/bb760352), как описано в Windows SDK.  
  
##  <a name="create"></a>  CToolTipCtrl::Create  
 Создание элемента управления всплывающей подсказки и прикрепляет его к `CToolTipCtrl` объекта.  
  
```  
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указывает родительского окна элемента управления всплывающей подсказки, обычно `CDialog`. Он не должен быть **NULL**.  
  
 `dwStyle`  
 Задает стиль управления всплывающей подсказки. В разделе **примечания** Дополнительные сведения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CToolTipCtrl` объекта успешно создан; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CToolTipCtrl` в два этапа. Во-первых, вызовите конструктор для создания `CToolTipCtrl` объекта, а затем вызвать **создать** Создание управления всплывающей подсказки и присоединить его к `CToolTipCtrl` объекта.  
  
 `dwStyle` Параметр может иметь любое сочетание [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles). Кроме того, всплывающая подсказка имеет два стиля данного класса: **TTS_ALWAYSTIP** и **TTS_NOPREFIX**.  
  
|Стиль|Значение|  
|-----------|-------------|  
|**TTS_ALWAYSTIP**|Указывает, что всплывающая подсказка будет отображаться при прохождении курсора над инструментом, независимо от того, окно-владелец управления всплывающей подсказки активным или неактивным. Без этого стиля всплывающая подсказка появляется при активном окно владелец, но не в том случае, когда он неактивен.|  
|**TTS_NOPREFIX**|Этот стиль предотвращает удаление из строкового амперсанд (&). Если нет элемента управления всплывающей подсказки **TTS_NOPREFIX** стиля, система автоматически удаляет символы амперсанда, что позволяет приложению использовать ту же строку, элемент меню, а текст элемента управления всплывающей подсказки.|  
  
 Всплывающая подсказка имеет `WS_POPUP` и **WS_EX_TOOLWINDOW** стили окна, независимо от их при создании элемента управления.  
  
 Для создания элемента управления всплывающей подсказки с помощью windows расширенных стилей, вызовите [CToolTipCtrl::CreateEx](#createex) вместо **создать**.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="createex"></a>  CToolTipCtrl::CreateEx  
 Создает элемент управления (дочернего окна) и связать его с `CToolTipCtrl` объекта.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwStyle = 0,  
    DWORD dwStyleEx = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `dwStyle`  
 Задает стиль управления всплывающей подсказки. В разделе **примечания** раздел [создать](#create) для получения дополнительной информации.  
  
 *dwStyleEx*  
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успешного выполнения в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо **создать** для применения расширенные стили Windows, заданные вводной части расширенный стиль Windows **WS_EX_**.  
  
##  <a name="ctooltipctrl"></a>  CToolTipCtrl::CToolTipCtrl  
 Создает объект `CToolTipCtrl`.  
  
```  
CToolTipCtrl();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать **создать** после создания объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]  
  
##  <a name="deltool"></a>  CToolTipCtrl::DelTool  
 Удаляет заданные `pWnd` и `nIDTool` из коллекции средств, поддерживаемых элементом управления всплывающей подсказки.  
  
```  
void DelTool(
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, содержащей это средство.  
  
 `nIDTool`  
 Идентификатор средства.  
  
##  <a name="getbubblesize"></a>  CToolTipCtrl::GetBubbleSize  
 Получает размер всплывающей подсказки.  
  
```  
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpToolInfo`  
 Указатель на всплывающей подсказки [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер всплывающей подсказки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_GETBUBBLESIZE](http://msdn.microsoft.com/library/windows/desktop/bb760387), как описано в Windows SDK.  
  
##  <a name="getcurrenttool"></a>  CToolTipCtrl::GetCurrentTool  
 Получает сведения, такие как размер, положение и текст окна всплывающей подсказки, отображаемый элементом текущего элемента управления всплывающей подсказки.  
  
```  
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `lpToolInfo`|Указатель на [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) структуры, который получает сведения о текущем окно всплывающей подсказки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если данные получены успешно. в противном случае `false.`  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TTM_GETCURRENTTOOL](http://msdn.microsoft.com/library/windows/desktop/bb760389) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода извлекает сведения о текущем окно всплывающей подсказки.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]  
  
##  <a name="getdelaytime"></a>  CToolTipCtrl::GetDelayTime  
 Получает начальный всплывающего окна и reshow длительности, заданных в настоящее время для элемента управления всплывающей подсказки.  
  
```  
int GetDelayTime(DWORD dwDuration) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `dwDuration`  
 Флаг, указывающий, какие значения длительности, будет возвращен. Этот параметр может принимать одно из следующих значений:  
  
- `TTDT_AUTOPOP` Получить количество времени отображения подсказки при указатель мыши останавливается внутри ограничивающего прямоугольника это средство.  
  
- `TTDT_INITIAL` Получить длину раз, когда указатель мыши должен оставаться в границах внутри ограничивающего прямоугольника это средство, до появления подсказки.  
  
- `TTDT_RESHOW` Получить время, необходимое для последующих окнами подсказка отображаться перемещении указателя мыши с одного инструмента в другое.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Время заданной задержки в миллисекундах  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_GETDELAYTIME](http://msdn.microsoft.com/library/windows/desktop/bb760390), как описано в Windows SDK.  
  
##  <a name="getmargin"></a>  CToolTipCtrl::GetMargin  
 Получает начало, левую, нижнюю и правого полей для подсказки.  
  
```  
void GetMargin(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lprc`  
 Адрес `RECT` структуру, которая будет получать данные поля. Члены [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры не определяют ограничивающего прямоугольника. С целью данное сообщение члены структуры интерпретируются следующим образом:  
  
|Член|Представление|  
|------------|--------------------|  
|**top**|Расстояние между верхней границей и вверху текст подсказки, в пикселях.|  
|**left**|Расстояние между левой границей и левый конец текст подсказки, в пикселях.|  
|**Вниз**|Расстояние между нижней границей и нижней части текст подсказки, в пикселях.|  
|**right**|Расстояние между правой границей и правом конце текст подсказки, в пикселях.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_GETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760391), как описано в Windows SDK.  
  
##  <a name="getmaxtipwidth"></a>  CToolTipCtrl::GetMaxTipWidth  
 Возвращает максимальную ширину для подсказки.  
  
```  
int GetMaxTipWidth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальная ширина подсказки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_GETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760392), как описано в Windows SDK.  
  
##  <a name="gettext"></a>  CToolTipCtrl::GetText  
 Извлекает текст, который поддерживает всплывающая подсказка для средства.  
  
```  
void GetText(
    CString& str,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `str`  
 Ссылка на `CString` объект, получающий текст данного средства.  
  
 `pWnd`  
 Указатель на окно, содержащей это средство.  
  
 `nIDTool`  
 Идентификатор средства.  
  
### <a name="remarks"></a>Примечания  
 `pWnd` И `nIDTool` параметры определяют средство. Если средство ранее зарегистрированного с элементом управления всплывающей подсказки посредством предыдущего вызова **CToolTipCtrl::AddTool**, объект, упоминаемый в `str` текст средства назначен параметр.  
  
##  <a name="gettipbkcolor"></a>  CToolTipCtrl::GetTipBkColor  
 Возвращает цвет фона в окне инструментов подсказки.  
  
```  
COLORREF GetTipBkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, представляющее цвет фона.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_GETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760394), как описано в Windows SDK.  
  
##  <a name="gettiptextcolor"></a>  CToolTipCtrl::GetTipTextColor  
 Возвращает цвет текста в окне инструментов подсказки.  
  
```  
COLORREF GetTipTextColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, представляющее цвет текста.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_GETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760395), как описано в Windows SDK.  
  
##  <a name="gettitle"></a>  CToolTipCtrl::GetTitle  
 Возвращает название текущего элемента управления всплывающей подсказки.  
  
```  
void GetTitle(PTTGETTITLE pttgt) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `pttgt`|Указатель на [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260) структуру, содержащую сведения об элементе управления ToolTip. По возвращении из этого метода `pszTitle` членом [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260) структуры точек для текста заголовка.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TTM_GETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760396) сообщение, которое описано в Windows SDK.  
  
##  <a name="gettoolcount"></a>  CToolTipCtrl::GetToolCount  
 Возвращает число инструментов, зарегистрированные с элементом управления всплывающей подсказки.  
  
```  
int GetToolCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число средств зарегистрирован с элементом управления всплывающей подсказки.  
  
##  <a name="gettoolinfo"></a>  CToolTipCtrl::GetToolInfo  
 Извлекает сведения о средстве, обслуживает всплывающая подсказка.  
  
```  
BOOL GetToolInfo(
    CToolInfo& ToolInfo,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ToolInfo*  
 Ссылка на `TOOLINFO` объект, получающий текст данного средства.  
  
 `pWnd`  
 Указатель на окно, содержащей это средство.  
  
 `nIDTool`  
 Идентификатор средства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 **Hwnd** и **uId** члены [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) ссылается структура *CToolInfo* средство идентификации. Если этот инструмент был зарегистрирован с элементом управления всплывающей подсказки посредством предыдущего вызова `AddTool`, `TOOLINFO` структура заполняется информацию об этом инструменте.  
  
##  <a name="hittest"></a>  CToolTipCtrl::HitTest  
 Проверяет, точки, чтобы определить, является ли оно внутри ограничивающего прямоугольника данное средство и если да, получить информацию об этом инструменте.  
  
```  
BOOL HitTest(
    CWnd* pWnd,  
    CPoint pt,  
    LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, содержащей это средство.  
  
 `pt`  
 Указатель на `CPoint` объект, содержащий координаты точки, которое необходимо проверить.  
  
 `lpToolInfo`  
 Указатель на [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) структуру, содержащую сведения об этом инструменте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если точку, указанную информацию проверки нажатия находится внутри ограничивающего прямоугольника средства; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если эта функция возвращает ненулевое значение, структура указывает `lpToolInfo` содержатся сведения о средстве, в которой прямоугольник находится точка.  
  
 `TTHITTESTINFO` Структура определяется следующим образом:  
  
 `typedef struct _TT_HITTESTINFO { // tthti`  
  
 `HWND hwnd;   // handle of tool or window with tool`  
  
 `POINT pt;    // client coordinates of point to test`  
  
 `TOOLINFO ti; // receives information about the tool`  
  
 `} TTHITTESTINFO, FAR * LPHITTESTINFO;`  
  
 **HWND**  
 Указывает дескриптор этого средства.  
  
 **pt**  
 Задает координаты точки, если точка находится в средстве ограничивающего прямоугольника.  
  
 **Логики операций со временем**  
 Сведения о средстве. Дополнительные сведения о `TOOLINFO` структуры см. в разделе [CToolTipCtrl::GetToolInfo](#gettoolinfo).  
  
##  <a name="pop"></a>  CToolTipCtrl::Pop  
 Удаляет отображаемые подсказки в представлении.  
  
```  
void Pop();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_POP](http://msdn.microsoft.com/library/windows/desktop/bb760401), как описано в Windows SDK.  
  
##  <a name="popup"></a>  CToolTipCtrl::Popup  
 Вызывает текущего элемента управления всплывающей подсказки для отображения в координатах последнее сообщение мыши.  
  
```  
void Popup();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TTM_POPUP](http://msdn.microsoft.com/library/windows/desktop/bb760402) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода отображается окно всплывающей подсказки.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]  
  
##  <a name="relayevent"></a>  CToolTipCtrl::RelayEvent  
 Передает сообщение мыши элементом управления всплывающей подсказки для обработки.  
  
```  
void RelayEvent(LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMsg`  
 Указатель на [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) структуру, содержащую сообщения для ретрансляции.  
  
### <a name="remarks"></a>Примечания  
 Всплывающая подсказка обрабатывает только следующие сообщения, отправляемые ему из `RelayEvent`:  
  
|WM_LBUTTONDOWN|WM_MOUSEMOVE|  
|---------------------|-------------------|  
|`WM_LBUTTONUP`|`WM_RBUTTONDOWN`|  
|`WM_MBUTTONDOWN`|`WM_RBUTTONUP`|  
|`WM_MBUTTONUP`||  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="setdelaytime"></a>  CToolTipCtrl::SetDelayTime  
 Задает время задержки для элемента управления всплывающей подсказки.  
  
```  
void SetDelayTime(UINT nDelay);

 
void SetDelayTime(
    DWORD dwDuration,  
    int iTime);
```  
  
### <a name="parameters"></a>Параметры  
 *nDelay*  
 Задает новое время задержки в миллисекундах.  
  
 `dwDuration`  
 Флаг, указывающий, какие значения длительности, будет возвращен. В разделе [CToolTipCtrl::GetDelayTime](#getdelaytime) описание допустимых значений.  
  
 *iTime*  
 Время заданной задержки в миллисекундах.  
  
### <a name="remarks"></a>Примечания  
 Задержка — это количество раз, когда указатель мыши должен оставаться над инструментом до появления подсказки. Время задержки по умолчанию — 500 миллисекунд.  
  
##  <a name="setmargin"></a>  CToolTipCtrl::SetMargin  
 Задает начало, левую, нижнюю и правого полей для подсказки.  
  
```  
void SetMargin(LPRECT lprc);
```  
  
### <a name="parameters"></a>Параметры  
 `lprc`  
 Адрес `RECT` структуру, содержащую сведения поля требуется задать. Члены `RECT` структуры не определяют ограничивающего прямоугольника. В разделе [CToolTipCtrl::GetMargin](#getmargin) описание поля данных.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_SETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760406), как описано в Windows SDK.  
  
##  <a name="setmaxtipwidth"></a>  CToolTipCtrl::SetMaxTipWidth  
 Задает максимальную ширину для подсказки.  
  
```  
int SetMaxTipWidth(int iWidth);
```  
  
### <a name="parameters"></a>Параметры  
 *iWidth*  
 Ширина окна подсказки максимальное средства требуется задать.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина предыдущего максимальное подсказки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_SETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760408), как описано в Windows SDK.  
  
##  <a name="settipbkcolor"></a>  CToolTipCtrl::SetTipBkColor  
 Задает цвет фона в окне инструментов подсказки.  
  
```  
void SetTipBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 `clr`  
 Новый цвет фона.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_SETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760411), как описано в Windows SDK.  
  
##  <a name="settiptextcolor"></a>  CToolTipCtrl::SetTipTextColor  
 Задает цвет текста в окне инструментов подсказки.  
  
```  
void SetTipTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 `clr`  
 Новый цвет текста.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_SETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760413), как описано в Windows SDK.  
  
##  <a name="settitle"></a>  CToolTipCtrl::SetTitle  
 Добавляет стандартную строку, значок и заголовок подсказки.  
  
```  
BOOL SetTitle(
    UINT uIcon,  
    LPCTSTR lpstrTitle);
```  
  
### <a name="parameters"></a>Параметры  
 *uIcon*  
 В разделе *значок* в [TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414) в Windows SDK.  
  
 *lpstrTitle*  
 Указатель на строку заголовка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414), как описано в Windows SDK.  
  
##  <a name="settoolinfo"></a>  CToolTipCtrl::SetToolInfo  
 Задает сведения, которые поддерживает во всплывающей подсказке инструмента.  
  
```  
void SetToolInfo(LPTOOLINFO lpToolInfo);
```  
  
### <a name="parameters"></a>Параметры  
 `lpToolInfo`  
 Указатель на [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) структура, которая задает сведения для установки.  
  
##  <a name="settoolrect"></a>  CToolTipCtrl::SetToolRect  
 Задает ограничивающий прямоугольник для средства.  
  
```  
void SetToolRect(
    CWnd* pWnd,  
    UINT_PTR nIDTool,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, содержащей это средство.  
  
 `nIDTool`  
 Идентификатор средства.  
  
 `lpRect`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура ограничивающий прямоугольник.  
  
##  <a name="setwindowtheme"></a>  CToolTipCtrl::SetWindowTheme  
 Задает визуальный стиль подсказки.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Параметры  
 `pszSubAppName`  
 Указатель на строку Юникода, содержит визуальный стиль для задания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение не используется.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [TTM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb760418) сообщения, как описано в Windows SDK.  
  
##  <a name="update"></a>  CToolTipCtrl::Update  
 Вызывает перерисовку текущего инструмента.  
  
```  
void Update();
```  
  
##  <a name="updatetiptext"></a>  CToolTipCtrl::UpdateTipText  
 Обновляет текст подсказки для элемента управления средств.  
  
```  
void UpdateTipText(
    LPCTSTR lpszText,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);

 
void UpdateTipText(
    UINT nIDText,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszText`  
 Указатель на текст для средства.  
  
 `pWnd`  
 Указатель на окно, содержащей это средство.  
  
 `nIDTool`  
 Идентификатор средства.  
  
 `nIDText`  
 Идентификатор строкового ресурса, содержащий текст для средства.  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CToolBar](../../mfc/reference/ctoolbar-class.md)
