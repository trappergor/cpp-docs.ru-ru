---
title: "CControlBar-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CControlBar
- AFXEXT/CControlBar
- AFXEXT/CControlBar::CControlBar
- AFXEXT/CControlBar::CalcDynamicLayout
- AFXEXT/CControlBar::CalcFixedLayout
- AFXEXT/CControlBar::CalcInsideRect
- AFXEXT/CControlBar::DoPaint
- AFXEXT/CControlBar::DrawBorders
- AFXEXT/CControlBar::DrawGripper
- AFXEXT/CControlBar::EnableDocking
- AFXEXT/CControlBar::GetBarStyle
- AFXEXT/CControlBar::GetBorders
- AFXEXT/CControlBar::GetCount
- AFXEXT/CControlBar::GetDockingFrame
- AFXEXT/CControlBar::IsFloating
- AFXEXT/CControlBar::OnUpdateCmdUI
- AFXEXT/CControlBar::SetBarStyle
- AFXEXT/CControlBar::SetBorders
- AFXEXT/CControlBar::SetInPlaceOwner
- AFXEXT/CControlBar::m_bAutoDelete
- AFXEXT/CControlBar::m_pInPlaceOwner
dev_langs:
- C++
helpviewer_keywords:
- CControlBar class
- OLE resize bars
- OLE resize bars, base class
- dialog bars, base class
- toolbars [C++], base class
- control bars [C++], base class
- status bars, base class
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
caps.latest.revision: 22
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 17702c4ca8559f1990cbbc183f1e409a6b2be484
ms.contentlocale: ru-ru
ms.lasthandoff: 03/31/2017

---
# <a name="ccontrolbar-class"></a>CControlBar Class
Базовый класс для классов панелей элементов управления [CStatusBar](../../mfc/reference/cstatusbar-class.md), [CToolBar](../../mfc/reference/ctoolbar-class.md), [CDialogBar](../../mfc/reference/cdialogbar-class.md), [CReBar](../../mfc/reference/crebar-class.md), и [COleResizeBar](../../mfc/reference/coleresizebar-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CControlBar : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CControlBar::CControlBar](#ccontrolbar)|Создает объект `CControlBar`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CControlBar::CalcDynamicLayout](#calcdynamiclayout)|Возвращает размер полосы динамический элемент управления как [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.|  
|[CControlBar::CalcFixedLayout](#calcfixedlayout)|Возвращает размер панели элементов управления, как [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.|  
|[CControlBar::CalcInsideRect](#calcinsiderect)|Возвращает текущие измерения области панели управления. включая границы.|  
|[CControlBar::DoPaint](#dopaint)|Отображает границы и захватом панели элементов управления.|  
|[CControlBar::DrawBorders](#drawborders)|Отображает границы панели элементов управления.|  
|[CControlBar::DrawGripper](#drawgripper)|Отрисовывает границу панели элементов управления.|  
|[CControlBar::EnableDocking](#enabledocking)|Позволяет панель элементов управления, закрепляться или с плавающей запятой.|  
|[CControlBar::GetBarStyle](#getbarstyle)|Извлекает параметры стиля панели управления.|  
|[CControlBar::GetBorders](#getborders)|Извлекает значения границы панели элементов управления.|  
|[CControlBar::GetCount](#getcount)|Возвращает количество отличных `HWND` элементы на панели управления.|  
|[CControlBar::GetDockingFrame](#getdockingframe)|Возвращает указатель на фрейм, к которому подключено панель элементов управления.|  
|[CControlBar::IsFloating](#isfloating)|Возвращает ненулевое значение, если панель элементов управления в панель элементов управления с плавающей запятой.|  
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|Вызывает обработчики команды пользовательского интерфейса.|  
|[CControlBar::SetBarStyle](#setbarstyle)|Изменяет параметры стиля панели управления.|  
|[CControlBar::SetBorders](#setborders)|Задает значения границы панели элементов управления.|  
|[CControlBar::SetInPlaceOwner](#setinplaceowner)|Изменяет владельца на месте панели элементов управления.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CControlBar::m_bAutoDelete](#m_bautodelete)|Если значение ненулевое, `CControlBar` объект удаляется при удалении на панели управления Windows.|  
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|Владелец панели элементов управления на месте.|  
  
## <a name="remarks"></a>Примечания  
 Панель элементов управления представляет собой окно, обычно выравнивается слева или справа от фрейма окна. Он может содержать дочерние элементы, которые могут быть `HWND`- на основе элементов управления, которые являются windows, создающие и реагировать на сообщения Windows, или не - `HWND`-на основе элементов, которые не являются окнами и управляются с помощью кода приложения или код платформы. Списки и элементы управления редактирования являются примерами `HWND`- элементы управления на основе; панелей строки состояния и кнопок с точечными рисунками приведены примеры не - `HWND`-элементы управления на основе.  
  
 Панель элементов управления windows обычно являются дочерние окна родительское окно фрейма и обычно имеют общего родителя, представление клиента или клиента MDI окна фрейма. Объект `CControlBar` объект использует сведения о клиентской области родительского окна для размещения себя. Оповещает о том, сколько места остается нераспределенного в клиентской области родительского окна родительского окна.  
  
 Дополнительные сведения о `CControlBar`, см.:  
  
- [Панели элементов управления](../../mfc/control-bars.md)  
  
- [Техническое Примечание 31: Панели элементов управления](../../mfc/tn031-control-bars.md).  
  
-   Статья базы знаний Q242577: PRB: обновление команды пользовательского интерфейса обработчики не работают для вложенных меню в поле диалогового окна  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CControlBar`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxext.h  
  
##  <a name="calcdynamiclayout"></a>CControlBar::CalcDynamicLayout  
 Платформа вызывает эту функцию-член для вычисления размеров динамическую панель инструментов.  
  
```  
virtual CSize CalcDynamicLayout(
    int nLength,  
    DWORD nMode);
```  
  
### <a name="parameters"></a>Параметры  
 `nLength`  
 Запрошенный измерения панели элементов управления, горизонтальной или вертикальной, в зависимости от `dwMode`.  
  
 `nMode`  
 Следующие предопределенные флаги используются для определения высоты и ширины окна динамического управления. Оператор побитового или (|) для объединения флаги.  
  
|Флаги режима макета|Это означает|  
|-----------------------|-------------------|  
|`LM_STRETCH`|Указывает растягивания панели управления для размера кадра. Набор, если строка не закрепляемую панель (недоступно для закрепления). Не задан, если панель закреплена или с плавающей запятой (доступно для закрепления). Если задано, `LM_STRETCH` игнорирует `nLength` и возвращает измерений, основанных на `LM_HORZ` состояние. `LM_STRETCH`работает так же, как `bStretch` параметр, используемый в [CalcFixedLayout](#calcfixedlayout); см. Дополнительные сведения об отношениях между растяжения и ориентацию, функция-член.|  
|`LM_HORZ`|Указывает, что полоса является горизонтально или вертикально. Задайте, если в строке горизонтальный и вертикальный, если оно не задано. `LM_HORZ`работает так же, как `bHorz` параметр, используемый в [CalcFixedLayout](#calcfixedlayout); см. Дополнительные сведения об отношениях между растяжения и ориентацию, функция-член.|  
|**LM_MRUWIDTH**|Последние использовавшиеся динамического ширины. Игнорирует `nLength` параметр и использует сохраненных самые последние использовавшиеся ширины.|  
|`LM_HORZDOCK`|Горизонтальный закреплены измерений. Игнорирует `nLength` параметр и возвращает динамический размер с наибольшей шириной.|  
|`LM_VERTDOCK`|Вертикальная закреплены измерений. Игнорирует `nLength` параметр и возвращает динамический размер наибольшего высоты.|  
|`LM_LENGTHY`|Если `nLength` указывающее высоту (оси Y) вместо ширины.|  
|`LM_COMMIT`|Сбрасывает **LM_MRUWIDTH** для текущей ширины плавающей панели элементов управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 На панели управления размер в пикселях объекта [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию-член для предоставления собственных динамического макета в классах, производных от `CControlBar`. MFC-классы, производные от `CControlBar`, такие как [CToolbar](../../mfc/reference/ctoolbar-class.md), переопределить эту функцию-член и предоставить собственную реализацию.  
  
##  <a name="calcfixedlayout"></a>CControlBar::CalcFixedLayout  
 Вызовите эту функцию-член для вычисления горизонтальный размер панели элементов управления.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры  
 `bStretch`  
 Указывает ли панель растягивания для размера кадра. `bStretch` Параметр имеет ненулевое значение, при строке не закрепляемую панель (недоступно для закрепления) и 0 при закрепленными или с плавающей запятой (доступны для закрепления).  
  
 `bHorz`  
 Указывает, что полоса является горизонтально или вертикально. `bHorz` Параметр имеет ненулевое значение, если панель горизонтальный и равно 0, если она вертикально.  
  
### <a name="return-value"></a>Возвращаемое значение  
 На панели управления размер в пикселях объекта `CSize` объекта.  
  
### <a name="remarks"></a>Примечания  
 Панели элементов управления, таких как панели инструментов можно растянуть по горизонтали или по вертикали для размещения кнопок из панели управления.  
  
 Если `bStretch` — **TRUE**, растянуть измерения вдоль ориентацию, предоставляемые `bHorz`. Другими словами Если `bHorz` — **FALSE**, панель элементов управления растягивается по вертикали. Если `bStretch` — **FALSE**, stretch не происходит. Следующая таблица показывает возможных перестановок и полученный стилей панели элементов управления, из `bStretch` и `bHorz`.  
  
|bStretch|bHorz|Растяжение|Ориентация|Закрепление или не закрепления|  
|--------------|-----------|----------------|-----------------|--------------------------|  
|**ЗНАЧЕНИЕ TRUE**|**ЗНАЧЕНИЕ TRUE**|Горизонтальная растяжения|Горизонтально|Не закрепления|  
|**ЗНАЧЕНИЕ TRUE**|**ЗНАЧЕНИЕ FALSE**|Растяжение по вертикали|Вертикально|Не закрепления|  
|**ЗНАЧЕНИЕ FALSE**|**ЗНАЧЕНИЕ TRUE**|Без растяжения доступны|Горизонтально|Закрепление|  
|**ЗНАЧЕНИЕ FALSE**|**ЗНАЧЕНИЕ FALSE**|Без растяжения доступны|Вертикально|Закрепление|  
  
##  <a name="calcinsiderect"></a>CControlBar::CalcInsideRect  
 Платформа вызывает эту функцию для расчета клиентской области элемента панели управления.  
  
```  
virtual void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Содержит текущие размеры панели элементов управления; включая границы.  
  
 `bHorz`  
 Указывает, что полоса является горизонтально или вертикально. `bHorz` Параметр имеет ненулевое значение, если панель горизонтальный и равно 0, если она вертикально.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается до рисования на панели управления.  
  
 Переопределите эту функцию для настройки отображения границ и область захвата панели элементов управления.  
  
##  <a name="ccontrolbar"></a>CControlBar::CControlBar  
 Создает объект `CControlBar`.  
  
```  
CControlBar();
```  
  
##  <a name="dopaint"></a>CControlBar::DoPaint  
 Вызывается платформой для отрисовки границ и область захвата панели элементов управления.  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства, используемого для отрисовки границ и захватом панели элементов управления.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки поведения рисунка панели элементов управления.  
  
 Другой способ настройки является переопределение `DrawBorders` и `DrawGripper` функции и добавьте пользовательский код отрисовки для границ и захвата. Так как эти методы вызываются по умолчанию `DoPaint` метод, переопределенный `DoPaint` не требуется.  
  
##  <a name="drawborders"></a>CControlBar::DrawBorders  
 Вызывается платформой для отрисовки границ панели элементов управления.  
  
```  
virtual void DrawBorders(
    CDC* pDC,  
    CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства, используемого для отрисовки границ панели элементов управления.  
  
 `rect`  
 Объект `CRect` объект, содержащий измерения на панели управления.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки внешнего вида границ панели управления.  
  
##  <a name="drawgripper"></a>CControlBar::DrawGripper  
 Вызывается платформой для отрисовки захвата на панели управления.  
  
```  
virtual void DrawGripper(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указывает на контекст устройства для подготовки к просмотру границу панели управления.  
  
 `rect`  
 Объект `CRect` объект, содержащий измерения границу панели управления.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки внешнего вида границу панели управления.  
  
##  <a name="enabledocking"></a>CControlBar::EnableDocking  
 Вызывайте эту функцию, чтобы включить панель элементов управления можно закреплять.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDockStyle`  
 Указывает поддержке Закрепление панели элементов управления, так и его родительского окна, к которому могут быть закреплены на панели управления, если поддерживается. Может иметь одно или несколько из следующих:  
  
- `CBRS_ALIGN_TOP`Позволяет закрепления в верхней части клиентской области.  
  
- `CBRS_ALIGN_BOTTOM`Позволяет закрепления в нижней части клиентской области.  
  
- `CBRS_ALIGN_LEFT`Позволяет Закрепление левого края клиентской области.  
  
- `CBRS_ALIGN_RIGHT`Позволяет закрепления в правой части клиентской области.  
  
- `CBRS_ALIGN_ANY`Позволяет в любой части клиентской области закрепления.  
  
- `CBRS_FLOAT_MULTI`Позволяет несколько панелей элементов управления для перемещается в окна одной области.  
  
 Если значение равно 0 (то есть, указывающее флаги не) на панели управления не будет закреплен.  
  
### <a name="remarks"></a>Примечания  
 Указанных сторон должно соответствовать одной из сторон включено закрепление целевой фрейм окна, или этот фрейм окна нельзя закрепить панель элементов управления.  
  
##  <a name="getbarstyle"></a>CControlBar::GetBarStyle  
 Эта функция вызывается для определения того, какие **CBRS_** (стили панель управления) в настоящее время настроены для панели элементов управления.  
  
```  
DWORD GetBarStyle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий **CBRS_** (стили элемента управления полосы) параметры панели управления. В разделе [CControlBar::SetBarStyle](#setbarstyle) полный список доступных стилей.  
  
### <a name="remarks"></a>Примечания  
 Не обрабатывает **WS_** стили (стиль окна).  
  
##  <a name="getborders"></a>CControlBar::GetBorders  
 Возвращает текущие значения границы панели управления.  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CRect` объект, содержащий текущий ширину (в пикселях) каждой стороны объекта панели элементов управления. Например, значение `left` член из [CRect](../../atl-mfc-shared/reference/crect-class.md) , является ширину левой границы.  
  
##  <a name="getcount"></a>CControlBar::GetCount  
 Возвращает количество отличных `HWND` элементы на `CControlBar` объекта.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество отличных `HWND` элементы на `CControlBar` объекта. Эта функция возвращает 0 для [CDialogBar](../../mfc/reference/cdialogbar-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Тип элемента зависит от производного объекта: области для [CStatusBar](../../mfc/reference/cstatusbar-class.md) объектов и кнопки и разделители для [CToolBar](../../mfc/reference/ctoolbar-class.md) объектов.  
  
##  <a name="getdockingframe"></a>CControlBar::GetDockingFrame  
 Вызовите эту функцию-член для получения указателя на текущее окно фрейма, к которому закрепленной панели управления.  
  
```  
CFrameWnd* GetDockingFrame() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на окно фрейма, в случае успешного выполнения; в противном случае **NULL**.  
  
 Если панель элементов управления не закрепляются окно фрейма (то есть, если панель элементов управления с плавающей запятой), эта функция возвращает указатель в родительском [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md).  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о закрепляемых панелей см. в разделе [CControlBar::EnableDocking](#enabledocking) и [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).  
  
##  <a name="isfloating"></a>CControlBar::IsFloating  
 Вызовите эту функцию-член для определения с плавающей запятой или закрепленной панели управления.  
  
```  
BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если панель открывается как плавающее окно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Изменить состояние панели элементов управления из закреплено с плавающей запятой, вызовите [CFrameWnd::FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar).  
  
##  <a name="m_bautodelete"></a>CControlBar::m_bAutoDelete  
 Если значение ненулевое, `CControlBar` объект удаляется при удалении на панели управления Windows.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_bAutoDelete`— это открытая переменная типа **BOOL**.  
  
 Обычно объект панели управления является встроенным в объекте фреймового окна. В этом случае `m_bAutoDelete` равно 0, поскольку объект внедренные панель элементов управления уничтожается при уничтожении окна фрейма.  
  
 Присвойте этой переменной значение ненулевое значение, если выделить `CControlBar` объектов в куче и вы не планируете выполнять вызов **удалить**.  
  
##  <a name="m_pinplaceowner"></a>CControlBar::m_pInPlaceOwner  
 Владелец панели элементов управления на месте.  
  
```  
CWnd* m_pInPlaceOwner;  
```  
  
##  <a name="onupdatecmdui"></a>CControlBar::OnUpdateCmdUI  
 Эта функция-член вызывается платформой для обновления статуса панели инструментов и состояние.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 `pTarget`  
 Указывает фрейма главного окна приложения. Этот указатель используется для маршрутизации сообщений обновления.  
  
 `bDisableIfNoHndler`  
 Флаг, указывающий, должен ли элемент управления, который не имеет обновление обработчика автоматически отображается как отключенная.  
  
### <a name="remarks"></a>Примечания  
 Для обновления отдельных кнопки или области, используйте `ON_UPDATE_COMMAND_UI` макрос на карте сообщения правильно настроить обработчика обновлений. В разделе [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) Дополнительные сведения об использовании этого макроса.  
  
 `OnUpdateCmdUI`вызывается платформой, когда приложение находится в состоянии простоя. Окна фрейма обновления должен иметь дочернее окно, по крайней мере косвенно видимым фрейм окна. `OnUpdateCmdUI`существует расширенная overridable.  
  
##  <a name="setbarstyle"></a>CControlBar::SetBarStyle  
 Вызывайте эту функцию, чтобы задать нужный **CBRS_** стилей для панели элементов управления.  
  
```  
void SetBarStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Нужные стили для панели элементов управления. Может иметь одно или несколько из следующих:  
  
- `CBRS_ALIGN_TOP`Позволяет панели элементов управления, прикрепленные к верхней части клиентской области окна фрейма.  
  
- `CBRS_ALIGN_BOTTOM`Позволяет панели управления можно закреплять в нижнюю часть клиентской области окна фрейма.  
  
- `CBRS_ALIGN_LEFT`Позволяет панели управления можно закреплять левого края клиентской области окна фрейма.  
  
- `CBRS_ALIGN_RIGHT`Позволяет панели управления, чтобы закрепить в правой части клиентской области окна фрейма.  
  
- `CBRS_ALIGN_ANY`Позволяет панели управления, чтобы закрепить с любой стороны клиентской области окна фрейма.  
  
- `CBRS_BORDER_TOP`В результате границы, отображаемый в верхней части панели элементов управления, на которые будет видима.  
  
- `CBRS_BORDER_BOTTOM`В результате границы, отображаемый на нижней границе панели элементов управления, на которые будет видима.  
  
- `CBRS_BORDER_LEFT`В результате границы, отображаемый в левой панели элементов управления, на которые будет видима.  
  
- `CBRS_BORDER_RIGHT`В результате границы, отображаемый на правой стороне панели элементов управления, на которые будет видима.  
  
- `CBRS_FLOAT_MULTI`Позволяет несколько панелей элементов управления для перемещается в окна одной области.  
  
- `CBRS_TOOLTIPS`В результате всплывающие подсказки, отображаемый для панели элементов управления.  
  
- `CBRS_FLYBY`Вызывает обновление в то же время, как всплывающие подсказки текста сообщения.  
  
- **CBRS_GRIPPER** вызывает захвата, аналогичной используемой полосами в **CReBar** объекта, отображаемый для любого `CControlBar`-производного класса.  
  
### <a name="remarks"></a>Примечания  
 Не влияет на **WS_** параметры (стиль окна).  
  
##  <a name="setborders"></a>CControlBar::SetBorders  
 Вызывайте эту функцию, чтобы задать размер границ панели управления.  
  
```  
void SetBorders(
    int cxLeft = 0,  
    int cyTop = 0,  
    int cxRight = 0,  
    int cyBottom = 0);  
  
void SetBorders(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 *cxLeft*  
 Ширина (в пикселях) левой границы панели управления.  
  
 *cyTop*  
 Высота (в пикселях) верхней границы панели управления.  
  
 *cxRight*  
 Ширина правой границы панели элементов управления (в пикселях).  
  
 *cyBottom*  
 Высота (в пикселях) границы нижней панели управления.  
  
 `lpRect`  
 Указатель на [CRect](../../atl-mfc-shared/reference/crect-class.md) объект, содержащий текущий ширину (в пикселях) границы каждого объекта панели элементов управления.  
  
### <a name="example"></a>Пример  
 В следующем примере кода устанавливает верхние и нижние границы панели элементов управления на 5 пикселей и левую и правую границы 2 пикселя:  
  
 [!code-cpp[NVC_MFCControlLadenDialog #61](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]  
  
##  <a name="setinplaceowner"></a>CControlBar::SetInPlaceOwner  
 Изменяет владельца на месте панели элементов управления.  
  
```  
void SetInPlaceOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на объект `CWnd`.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CTRLBARS](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CToolBar-класс](../../mfc/reference/ctoolbar-class.md)   
 [CDialogBar-класс](../../mfc/reference/cdialogbar-class.md)   
 [CStatusBar-класс](../../mfc/reference/cstatusbar-class.md)   
 [Класс CReBar](../../mfc/reference/crebar-class.md)

