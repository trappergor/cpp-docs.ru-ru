---
title: "CToolTipCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- tool tips [C++], tool tip controls
- data tips [C++]
- CToolTipCtrl class
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
caps.latest.revision: 20
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
ms.openlocfilehash: 982aae01dc1308896e9c625e2c2e118b65ec2e64
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl Class
Инкапсулирует функциональность элемента управления "всплывающая подсказка" — небольшого всплывающего окна, в котором отображается одна строка текста, описывающая назначение инструмента в приложении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CToolTipCtrl::CToolTipCtrl](#ctooltipctrl)|Создает объект `CToolTipCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CToolTipCtrl::Activate](#activate)|Активирует и деактивирует управления всплывающей подсказки.|  
|[CToolTipCtrl::AddTool](#addtool)|Регистрирует средство управления всплывающей подсказки.|  
|[CToolTipCtrl::AdjustRect](#adjustrect)|Преобразование между текстом элемента управления всплывающей подсказки отобразить прямоугольник и ее прямоугольника окна.|  
|[CToolTipCtrl::Create](#create)|Создание элемента управления всплывающей подсказки и присоединяет его к `CToolTipCtrl` объекта.|  
|[CToolTipCtrl::CreateEx](#createex)|Создает элемента управления всплывающей подсказки с указанным расширенные стили Windows и присоединяет его к `CToolTipCtrl` объекта.|  
|[CToolTipCtrl::DelTool](#deltool)|Удаляет средство с элементом управления всплывающей подсказки.|  
|[CToolTipCtrl::GetBubbleSize](#getbubblesize)|Получает размер всплывающей подсказки.|  
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|Извлекает сведения, такие как размер, положение и текст окна всплывающей подсказки, который отображает текущий элемент управления всплывающей подсказки.|  
|[CToolTipCtrl::GetDelayTime](#getdelaytime)|Получает начальный, всплывающие окна и reshow длительности, заданные в настоящее время средство управления подсказки.|  
|[CToolTipCtrl::GetMargin](#getmargin)|Извлекает сверху, слева, снизу и правого поля, заданные для подсказки.|  
|[CToolTipCtrl::GetMaxTipWidth](#getmaxtipwidth)|Получает максимальную ширину для подсказки.|  
|[CToolTipCtrl::GetText](#gettext)|Получает текст, который поддерживает средство управления всплывающей подсказки.|  
|[CToolTipCtrl::GetTipBkColor](#gettipbkcolor)|Получает цвет фона в подсказки.|  
|[CToolTipCtrl::GetTipTextColor](#gettiptextcolor)|Получает цвет текста в окне подсказки инструментов.|  
|[CToolTipCtrl::GetTitle](#gettitle)|Возвращает название текущего элемента управления всплывающей подсказки.|  
|[CToolTipCtrl::GetToolCount](#gettoolcount)|Получает количество средств, поддерживаемых элементом управления всплывающей подсказки.|  
|[CToolTipCtrl::GetToolInfo](#gettoolinfo)|Возвращает сведения, поддерживающий управления всплывающей подсказки о средстве.|  
|[CToolTipCtrl::HitTest](#hittest)|Проверяет точку, чтобы определить, является ли оно внутри ограничивающего прямоугольника данное средство. В этом случае извлекает сведения о средстве.|  
|[CToolTipCtrl::Pop](#pop)|Удаляет отображаемые подсказки из представления.|  
|[CToolTipCtrl::Popup](#popup)|Вызывает текущий элемент управления всплывающей подсказки для отображения в координатах последнего сообщения мыши.|  
|[CToolTipCtrl::RelayEvent](#relayevent)|Передает сообщение мыши элементом управления всплывающей подсказки для обработки.|  
|[CToolTipCtrl::SetDelayTime](#setdelaytime)|Задает начальный всплывающем и reshow длительности для элемента управления всплывающей подсказки.|  
|[CToolTipCtrl::SetMargin](#setmargin)|Задает начало, левую, нижнюю и правого поля для подсказки.|  
|[CToolTipCtrl::SetMaxTipWidth](#setmaxtipwidth)|Задает максимальную ширину для подсказки.|  
|[CToolTipCtrl::SetTipBkColor](#settipbkcolor)|Задает цвет фона в подсказки.|  
|[CToolTipCtrl::SetTipTextColor](#settiptextcolor)|Задает цвет текста в окне подсказки инструментов.|  
|[CToolTipCtrl::SetTitle](#settitle)|Добавляет стандартную строку значок и заголовок подсказки.|  
|[CToolTipCtrl::SetToolInfo](#settoolinfo)|Задает сведения, которые поддерживает всплывающей подсказки для инструмента.|  
|[CToolTipCtrl::SetToolRect](#settoolrect)|Задает ограничивающий прямоугольник для средства.|  
|[CToolTipCtrl::SetWindowTheme](#setwindowtheme)|Задает стиль оформления подсказки.|  
|[CToolTipCtrl::Update](#update)|Вызывает перерисовку текущего инструмента.|  
|[CToolTipCtrl::UpdateTipText](#updatetiptext)|Задает текст подсказки для инструмента.|  
  
## <a name="remarks"></a>Примечания  
 «Средства» является либо окна, такие как дочернего окна или элемента управления или определяемые приложением прямоугольной области в клиентской области окна. Во всплывающей подсказке скрыто в большинстве случаев отображаются, только когда пользователь помещает курсор над средством и оставляет его на примерно половину второй. Подсказка появляется рядом с курсором и исчезает, когда пользователь нажимает кнопку мыши или перемещает курсор средство.  
  
 `CToolTipCtrl`предоставляет функциональные возможности для управления начальное время и длительность всплывающей подсказки, ширина полей, окружающих текст подсказки, ширина подсказки сам и цвет фона и текст всплывающей подсказки. Единое средство управления подсказки может предоставить сведения для более чем одного средства.  
  
 `CToolTipCtrl` Класс предоставляет функциональные возможности элемента управления Windows распространенных всплывающая подсказка. Этот элемент управления (и, следовательно, `CToolTipCtrl` класса) доступны только для программы под управлением версий Windows 95/98 и Windows NT 3.51 и более поздних версий.  
  
 Дополнительные сведения о включении всплывающие подсказки в разделе [всплывающие подсказки в Windows, не являющиеся производными CFrameWnd](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
 Дополнительные сведения об использовании `CToolTipCtrl`, в разделе [управления](../../mfc/controls-mfc.md) и [CToolTipCtrl с помощью](../../mfc/using-ctooltipctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolTipCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="activate"></a>CToolTipCtrl::Activate  
 Эта функция вызывается для активации или деактивации управления всплывающей подсказки.  
  
```  
void Activate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 `bActivate`  
 Указывает, является ли элемент управления всплывающей подсказки для активации или деактивации.  
  
### <a name="remarks"></a>Примечания  
 Если `bActivate` — **TRUE**, элемент активизирован; Если **FALSE**, он отключен.  
  
 При активном управления всплывающей подсказки совет сведений о программе появляется при прохождении курсора над средством, которое регистрируется с элементом управления; Если неактивен, средство совет сведения не отображается, даже когда курсор находится над средством.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="addtool"></a>CToolTipCtrl::AddTool  
 Регистрирует средство управления всплывающей подсказки.  
  
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
 Указатель на окно, содержащее средство.  
  
 `nIDText`  
 Идентификатор строкового ресурса с текстом программы.  
  
 *lpRectTool*  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, содержащую средство координаты ограничивающего прямоугольника. Координаты указываются относительно левого верхнего угла клиентской области окна, идентифицируемый `pWnd`.  
  
 `nIDTool`  
 Идентификатор средства.  
  
 `lpszText`  
 Указатель на текст программы. Если этот параметр имеет значение **LPSTR_TEXTCALLBACK**, **TTN_NEEDTEXT** сообщений уведомления перейти к родительского окна, `pWnd` указывает.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 **LpRectTool** и **nIDTool** параметры должны быть допустимым, или если **lpRectTool** имеет значение NULL, **nIDTool** должно быть равно 0.  
  
 Элемента управления всплывающей подсказки может быть связан более чем одного средства. Эта функция вызывается для регистрации средство управления всплывающей подсказки для отображения сведений, хранящихся в подсказке, когда курсор находится в средстве.  
  
> [!NOTE]
>  Невозможно задать всплывающую подсказку в статический элемент управления с помощью `AddTool`.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="adjustrect"></a>CToolTipCtrl::AdjustRect  
 Преобразование между текст всплывающей подсказки элемента управления отображения прямоугольника и ее прямоугольника окна.  
  
```  
BOOL AdjustRect(
    LPRECT lprc,  
    BOOL bLarger = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `lprc`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, которая содержит прямоугольник окна средства совет или прямоугольник отображения текста.  
  
 `bLarger`  
 Если **TRUE**, `lprc` используется для указания прямоугольник отображения текста, и она получает соответствующие прямоугольника окна. Если **FALSE**, `lprc` используется для указания прямоугольника окна, и он получает соответствующий прямоугольник отображения текста.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если прямоугольник успешно изменены; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вычисляет прямоугольник отображения элемента управления всплывающей подсказки в текст из окна прямоугольника или прямоугольника окна совет средства, необходимые для отображения прямоугольник отображения указанного текста.  
  
 Эта функция-член реализует поведение сообщения Win32 [TTM_ADJUSTRECT](http://msdn.microsoft.com/library/windows/desktop/bb760352), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="create"></a>CToolTipCtrl::Create  
 Создание элемента управления всплывающей подсказки и присоединяет его к `CToolTipCtrl` объекта.  
  
```  
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указывает родительского окна управления всплывающей подсказки, обычно `CDialog`. Оно не должно быть **NULL**.  
  
 `dwStyle`  
 Задает стиль элемента управления всплывающей подсказки. В разделе **примечания** Дополнительные сведения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CToolTipCtrl` объект успешно создан; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CToolTipCtrl` в два этапа. Во-первых, вызовите конструктор для создания `CToolTipCtrl` , а затем вызвать **создать** для создания управления всплывающей подсказки и присоединить его к `CToolTipCtrl` объекта.  
  
 `dwStyle` Параметр может иметь любое сочетание [стили окна](../../mfc/reference/window-styles.md). Кроме того, управления всплывающей подсказки имеет два стиля данного класса: **TTS_ALWAYSTIP** и **TTS_NOPREFIX**.  
  
|Стиль|Значение|  
|-----------|-------------|  
|**TTS_ALWAYSTIP**|Указывает, что подсказка будет появляться при прохождении курсора над средством, независимо от того, окна-владельца управления всплывающей подсказки активным или неактивным. Без этого стиля управления всплывающей подсказки отображается при активном окно владельца, но не находится в неактивном состоянии.|  
|**TTS_NOPREFIX**|Этот стиль предотвращает удаление знак амперсанда (&) из строки. Если нет элемента управления всплывающей подсказки **TTS_NOPREFIX** стиля, система автоматически удаляет знаки амперсанда, что позволяет приложению использовать ту же строку, элемент меню, а текст элемента управления всплывающей подсказки.|  
  
 Подсказка имеет `WS_POPUP` и **WS_EX_TOOLWINDOW** стили окна, независимо от их при создании элемента управления.  
  
 Создание элемента управления всплывающей подсказки с помощью windows расширенные стили, вызовите [CToolTipCtrl::CreateEx](#createex) вместо **создать**.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="createex"></a>CToolTipCtrl::CreateEx  
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
 Задает стиль элемента управления всплывающей подсказки. В разделе **примечания** раздел [создать](#create) для получения дополнительной информации.  
  
 *dwStyleEx*  
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успеха в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо **создать** для применения расширенных стилей Windows, заданные к ней префикс расширенный стиль Windows **WS_EX_**.  
  
##  <a name="ctooltipctrl"></a>CToolTipCtrl::CToolTipCtrl  
 Создает объект `CToolTipCtrl`.  
  
```  
CToolTipCtrl();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать **создать** после создания объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog&#74;](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]  
  
##  <a name="deltool"></a>CToolTipCtrl::DelTool  
 Удаляет заданные инструмент `pWnd` и `nIDTool` из коллекции средств, поддерживаемых элементом управления всплывающей подсказки.  
  
```  
void DelTool(
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, содержащее средство.  
  
 `nIDTool`  
 Идентификатор средства.  
  
##  <a name="getbubblesize"></a>CToolTipCtrl::GetBubbleSize  
 Получает размер всплывающей подсказки.  
  
```  
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpToolInfo`  
 Указатель на всплывающей подсказке [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер всплывающей подсказки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_GETBUBBLESIZE](http://msdn.microsoft.com/library/windows/desktop/bb760387), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcurrenttool"></a>CToolTipCtrl::GetCurrentTool  
 Извлекает сведения, такие как размер, положение и текст окна всплывающей подсказки, отображаемый элементом текущего элемента управления всплывающей подсказки.  
  
```  
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `lpToolInfo`|Указатель на [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) структуры, который получает сведения о текущем окно всплывающей подсказки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если данные извлекаются успешно; в противном случае —`false.`  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TTM_GETCURRENTTOOL](http://msdn.microsoft.com/library/windows/desktop/bb760389) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода извлекает сведения о текущем окно всплывающей подсказки.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1 №&6;](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]  
  
##  <a name="getdelaytime"></a>CToolTipCtrl::GetDelayTime  
 Получает начальный всплывающем и reshow длительности, установленный для элемента управления всплывающей подсказки.  
  
```  
int GetDelayTime(DWORD dwDuration) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `dwDuration`  
 Флаг, указывающий, какие значения длительности, будет возвращен. Этот параметр может принимать одно из следующих значений:  
  
- `TTDT_AUTOPOP`Получить время отображения подсказки при указатель мыши останавливается в это средство ограничивающего прямоугольника.  
  
- `TTDT_INITIAL`Получить время, указатель мыши должен оставаться в границах внутри ограничивающего прямоугольника инструмента, до появления подсказки.  
  
- `TTDT_RESHOW`Получить время, необходимое для последующих средство совет windows отображается как указатель перемещается от одного средства к другому.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Времени, в миллисекундах  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_GETDELAYTIME](http://msdn.microsoft.com/library/windows/desktop/bb760390), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getmargin"></a>CToolTipCtrl::GetMargin  
 Извлекает верхней, левой, нижней и правое поля для подсказки.  
  
```  
void GetMargin(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lprc`  
 Адрес `RECT` структуру, которая будет получать данные поля. Элементы [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры не определяют ограничивающего прямоугольника. Для этого сообщения члены структуры интерпретируются следующим образом:  
  
|Член|Представление|  
|------------|--------------------|  
|**top**|Расстояние между верхней границей и верхней части текст подсказки, в пикселях.|  
|**left**|Расстояние между левой границей и левый конец текст подсказки, в пикселях.|  
|**снизу**|Расстояние между нижней границей и нижней части текст подсказки, в пикселях.|  
|**right**|Расстояние между правой границей и правом конце текст подсказки, в пикселях.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_GETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760391), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getmaxtipwidth"></a>CToolTipCtrl::GetMaxTipWidth  
 Получает максимальную ширину для подсказки.  
  
```  
int GetMaxTipWidth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальная ширина для подсказки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_GETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760392), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettext"></a>CToolTipCtrl::GetText  
 Получает текст, который поддерживает средство управления всплывающей подсказки.  
  
```  
void GetText(
    CString& str,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `str`  
 Ссылка на `CString` объект, который получает текст данного средства.  
  
 `pWnd`  
 Указатель на окно, содержащее средство.  
  
 `nIDTool`  
 Идентификатор средства.  
  
### <a name="remarks"></a>Примечания  
 `pWnd` И `nIDTool` параметры определяют средство. Если это средство прежде зарегистрированы с элементом управления всплывающей подсказки по предыдущим вызовом **CToolTipCtrl::AddTool**, объект ссылается `str` средство текст назначен параметр.  
  
##  <a name="gettipbkcolor"></a>CToolTipCtrl::GetTipBkColor  
 Получает цвет фона в подсказки.  
  
```  
COLORREF GetTipBkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, представляющее цвет фона.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_GETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760394), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettiptextcolor"></a>CToolTipCtrl::GetTipTextColor  
 Получает цвет текста в окне подсказки инструментов.  
  
```  
COLORREF GetTipTextColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, представляющее цвет текста.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_GETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760395), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettitle"></a>CToolTipCtrl::GetTitle  
 Возвращает название текущего элемента управления всплывающей подсказки.  
  
```  
void GetTitle(PTTGETTITLE pttgt) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `pttgt`|Указатель на [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260) структуру, содержащую сведения об элементе управления ToolTip. По возвращении из этого метода `pszTitle` членом [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260) структуры точек для текста заголовка.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TTM_GETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760396) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettoolcount"></a>CToolTipCtrl::GetToolCount  
 Получает количество средств, зарегистрированные с элементом управления всплывающей подсказки.  
  
```  
int GetToolCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число средств зарегистрирован с элементом управления всплывающей подсказки.  
  
##  <a name="gettoolinfo"></a>CToolTipCtrl::GetToolInfo  
 Возвращает сведения, поддерживающий управления всплывающей подсказки о средстве.  
  
```  
BOOL GetToolInfo(
    CToolInfo& ToolInfo,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ToolInfo*  
 Ссылка на `TOOLINFO` объект, который получает текст данного средства.  
  
 `pWnd`  
 Указатель на окно, содержащее средство.  
  
 `nIDTool`  
 Идентификатор средства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 **Hwnd** и **uId** члены [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) ссылается структура *CToolInfo* средство идентификации. Если этот инструмент был зарегистрирован с элементом управления всплывающей подсказки по предыдущим вызовом `AddTool`, `TOOLINFO` структура заполняется сведения об этом средстве.  
  
##  <a name="hittest"></a>CToolTipCtrl::HitTest  
 Проверяет точку, чтобы определить, является ли оно внутри ограничивающего прямоугольника данное средство и если да, получить сведения о средстве.  
  
```  
BOOL HitTest(
    CWnd* pWnd,  
    CPoint pt,  
    LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, содержащее средство.  
  
 `pt`  
 Указатель на `CPoint` объект, содержащий координаты точки для тестирования.  
  
 `lpToolInfo`  
 Указатель на [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) структуру, содержащую сведения об этом средстве.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если точку, указанную информацию проверки нажатия находится внутри ограничивающего прямоугольника средства; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если эта функция возвращает ненулевое значение, структура указывает `lpToolInfo` заполняется сведения о средстве, в которой прямоугольник находится точка.  
  
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
  
 **TI**  
 Сведения о средстве. Дополнительные сведения о `TOOLINFO` структуры см. в разделе [CToolTipCtrl::GetToolInfo](#gettoolinfo).  
  
##  <a name="pop"></a>CToolTipCtrl::Pop  
 Удаляет отображаемые подсказки из представления.  
  
```  
void Pop();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_POP](http://msdn.microsoft.com/library/windows/desktop/bb760401), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="popup"></a>CToolTipCtrl::Popup  
 Вызывает текущий элемент управления всплывающей подсказки для отображения в координатах последнего сообщения мыши.  
  
```  
void Popup();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TTM_POPUP](http://msdn.microsoft.com/library/windows/desktop/bb760402) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода отображается окно всплывающей подсказки.  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]  
  
##  <a name="relayevent"></a>CToolTipCtrl::RelayEvent  
 Передает сообщение мыши элементом управления всплывающей подсказки для обработки.  
  
```  
void RelayEvent(LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMsg`  
 Указатель на [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) структуру, содержащую сообщения для ретрансляции.  
  
### <a name="remarks"></a>Примечания  
 Подсказка обрабатывает только следующие сообщения, отправляемые на него по `RelayEvent`:  
  
|WM_LBUTTONDOWN|WM_MOUSEMOVE|  
|---------------------|-------------------|  
|`WM_LBUTTONUP`|`WM_RBUTTONDOWN`|  
|`WM_MBUTTONDOWN`|`WM_RBUTTONUP`|  
|`WM_MBUTTONUP`||  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="setdelaytime"></a>CToolTipCtrl::SetDelayTime  
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
 Время задержки — это время, должны оставаться курсор над средством, до появления подсказки. Время задержки по умолчанию — 500 миллисекунд.  
  
##  <a name="setmargin"></a>CToolTipCtrl::SetMargin  
 Задает начало, левую, нижнюю и правого поля для подсказки.  
  
```  
void SetMargin(LPRECT lprc);
```  
  
### <a name="parameters"></a>Параметры  
 `lprc`  
 Адрес `RECT` структуру, содержащую сведения margin устанавливается. Элементы `RECT` структуры не определяют ограничивающего прямоугольника. В разделе [CToolTipCtrl::GetMargin](#getmargin) описание поля данных.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_SETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760406), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setmaxtipwidth"></a>CToolTipCtrl::SetMaxTipWidth  
 Задает максимальную ширину для подсказки.  
  
```  
int SetMaxTipWidth(int iWidth);
```  
  
### <a name="parameters"></a>Параметры  
 *iWidth*  
 Ширина окна подсказки максимальное средство устанавливается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина предыдущих максимальное tip.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_SETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760408), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="settipbkcolor"></a>CToolTipCtrl::SetTipBkColor  
 Задает цвет фона в подсказки.  
  
```  
void SetTipBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 `clr`  
 Новый цвет фона.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_SETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760411), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="settiptextcolor"></a>CToolTipCtrl::SetTipTextColor  
 Задает цвет текста в окне подсказки инструментов.  
  
```  
void SetTipTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 `clr`  
 Новый цвет текста.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_SETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760413), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="settitle"></a>CToolTipCtrl::SetTitle  
 Добавляет стандартную строку значок и заголовок подсказки.  
  
```  
BOOL SetTitle(
    UINT uIcon,  
    LPCTSTR lpstrTitle);
```  
  
### <a name="parameters"></a>Параметры  
 *uIcon*  
 В разделе *значок* в [TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *lpstrTitle*  
 Указатель на строку заголовка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="settoolinfo"></a>CToolTipCtrl::SetToolInfo  
 Задает сведения, которые поддерживает всплывающей подсказки для инструмента.  
  
```  
void SetToolInfo(LPTOOLINFO lpToolInfo);
```  
  
### <a name="parameters"></a>Параметры  
 `lpToolInfo`  
 Указатель на [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256) структура, содержащая сведения для установки.  
  
##  <a name="settoolrect"></a>CToolTipCtrl::SetToolRect  
 Задает ограничивающий прямоугольник для средства.  
  
```  
void SetToolRect(
    CWnd* pWnd,  
    UINT_PTR nIDTool,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, содержащее средство.  
  
 `nIDTool`  
 Идентификатор средства.  
  
 `lpRect`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура ограничивающий прямоугольник.  
  
##  <a name="setwindowtheme"></a>CToolTipCtrl::SetWindowTheme  
 Задает стиль оформления подсказки.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Параметры  
 `pszSubAppName`  
 Указатель на строку Юникода, содержит визуальный стиль для задания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение не используется.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [TTM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb760418) сообщений, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="update"></a>CToolTipCtrl::Update  
 Вызывает перерисовку текущего инструмента.  
  
```  
void Update();
```  
  
##  <a name="updatetiptext"></a>CToolTipCtrl::UpdateTipText  
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
 Указатель на текст программы.  
  
 `pWnd`  
 Указатель на окно, содержащее средство.  
  
 `nIDTool`  
 Идентификатор средства.  
  
 `nIDText`  
 Идентификатор строкового ресурса с текстом программы.  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CToolBar-класс](../../mfc/reference/ctoolbar-class.md)

