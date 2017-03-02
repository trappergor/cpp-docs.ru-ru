---
title: "CControlBar-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CControlBar
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9720c4c11656834923c0e42a2017d51543c08f53
ms.lasthandoff: 02/24/2017

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
|[CControlBar::CalcDynamicLayout](#calcdynamiclayout)|Возвращает размер окна динамический элемент управления в виде [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.|  
|[CControlBar::CalcFixedLayout](#calcfixedlayout)|Возвращает размер панели управления как [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.|  
|[CControlBar::CalcInsideRect](#calcinsiderect)|Возвращает текущие измерения области панели управления. включая границы.|  
|[CControlBar::DoPaint](#dopaint)|Отображает границы и захвата панели элементов управления.|  
|[CControlBar::DrawBorders](#drawborders)|Отображает границы панели элементов управления.|  
|[CControlBar::DrawGripper](#drawgripper)|Отображает границу панели управления.|  
|[CControlBar::EnableDocking](#enabledocking)|Позволяет быть закрепленными или плавающими панель элементов управления.|  
|[CControlBar::GetBarStyle](#getbarstyle)|Извлекает параметры стиля панели управления.|  
|[CControlBar::GetBorders](#getborders)|Извлекает значения границы панели элементов управления.|  
|[CControlBar::GetCount](#getcount)|Возвращает количество отличных `HWND` элементы в панели управления.|  
|[CControlBar::GetDockingFrame](#getdockingframe)|Возвращает указатель на фрейм, к которому прикреплено панель элементов управления.|  
|[CControlBar::IsFloating](#isfloating)|Возвращает ненулевое значение, если плавающей панели элементов управления в панели управления.|  
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|Вызывает обработчики команд пользовательского интерфейса.|  
|[CControlBar::SetBarStyle](#setbarstyle)|Изменяет параметры стиля панели управления.|  
|[CControlBar::SetBorders](#setborders)|Задает значения границы панели управления.|  
|[CControlBar::SetInPlaceOwner](#setinplaceowner)|Изменяет владельца на месте панели элементов управления.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CControlBar::m_bAutoDelete](#m_bautodelete)|Если значение ненулевое, `CControlBar` объект удаляется при удалении на панели управления Windows.|  
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|Владелец на месте панели управления.|  
  
## <a name="remarks"></a>Примечания  
 Панель элементов управления представляет собой окно, обычно выравнивается слева или справа от фрейма окна. Он может содержать дочерние элементы, которые могут быть `HWND`- на основе элементов управления, являющихся windows, которые создают и отвечать на сообщения Windows, или не - `HWND`-на основе элементов, которые не являются windows и управляются в коде приложения или код платформы. Списки и элементы управления редактирования являются примерами `HWND`- элементы управления на основе; панелей строки состояния и кнопки точечного рисунка приведены примеры не - `HWND`-на основе элементов управления.  
  
 Панель элементов управления windows, обычно дочерних окон родительской фреймового окна и обычно имеют общего родителя представление клиента или клиента MDI окна фрейма. Объект `CControlBar` объект использует сведения о клиентской области родительского окна для размещения сам. Оповещает о том, сколько места остается нераспределенного в клиентской области родительского окна родительского окна.  
  
 Дополнительные сведения о `CControlBar`, см.:  
  
- [Панели элементов управления](../../mfc/control-bars.md)  
  
- [Техническое Примечание 31: Панели элементов управления](../../mfc/tn031-control-bars.md).  
  
-   Статья базы знаний Q242577: PRB: обновление команд пользовательского интерфейса обработчики не работают для вложенных меню в диалоговое окно  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CControlBar`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле afxext.h  
  
##  <a name="a-namecalcdynamiclayouta--ccontrolbarcalcdynamiclayout"></a><a name="calcdynamiclayout"></a>CControlBar::CalcDynamicLayout  
 Платформа вызывает эту функцию-член для вычисления измерений динамическую панель инструментов.  
  
```  
virtual CSize CalcDynamicLayout(
    int nLength,  
    DWORD nMode);
```  
  
### <a name="parameters"></a>Параметры  
 `nLength`  
 Запрошенный измерения панели элементов управления горизонтальной или вертикальной, в зависимости от `dwMode`.  
  
 `nMode`  
 Следующие предопределенные флаги используются для определения высоты и ширины панели динамических элементов управления. Оператор побитового или (|) для объединения флаги.  
  
|Флаги режим макета|Это означает|  
|-----------------------|-------------------|  
|`LM_STRETCH`|Указывает, должен быть растянут на панели управления, размер рамки. Значение, если панель не прикрепляемые панели (недоступно для закрепления). Не устанавливается при панели закрепленными или плавающими (доступно для закрепления). Если задано, `LM_STRETCH` игнорирует `nLength` и возвращает измерений, основанных на `LM_HORZ` состояние. `LM_STRETCH`работает так же, как `bStretch` параметр, используемый в [CalcFixedLayout](#calcfixedlayout); см. Дополнительные сведения о связи между растяжение и ориентации этой функции-члена.|  
|`LM_HORZ`|Указывает, что полоса является горизонтально или вертикально. Задайте, если панели горизонтальный и вертикальный, если оно не задано. `LM_HORZ`работает так же, как `bHorz` параметр, используемый в [CalcFixedLayout](#calcfixedlayout); см. Дополнительные сведения о связи между растяжение и ориентации этой функции-члена.|  
|**LM_MRUWIDTH**|Последние использовавшиеся динамического ширины. Игнорирует `nLength` параметр и использует сохраненных самые последние использовавшиеся ширины.|  
|`LM_HORZDOCK`|Горизонтальный закреплено измерений. Игнорирует `nLength` параметр и возвращает динамического размера с наибольшей шириной.|  
|`LM_VERTDOCK`|Вертикальный закреплено измерений. Игнорирует `nLength` параметр и возвращает динамический размер наибольшего высоты.|  
|`LM_LENGTHY`|Если `nLength` указывает высоту (оси Y) вместо ширины.|  
|`LM_COMMIT`|Сбрасывает **LM_MRUWIDTH** для текущей ширины плавающей панели элементов управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Панель элементов управления размер в точках из [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию-член для предоставления динамический макет в классы, производные от `CControlBar`. MFC-классы, производные от `CControlBar`, такие как [CToolbar](../../mfc/reference/ctoolbar-class.md), переопределить эту функцию-член и предоставить свою собственную реализацию.  
  
##  <a name="a-namecalcfixedlayouta--ccontrolbarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CControlBar::CalcFixedLayout  
 Вызовите эту функцию-член для вычисления горизонтальный размер панели элементов управления.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры  
 `bStretch`  
 Указывает, должен быть растянут панели, размер рамки. `bStretch` Параметр имеет ненулевое значение, при панели не прикрепляемые панели (недоступно для закрепления) и 0 при закрепленными или плавающими (доступно для закрепления).  
  
 `bHorz`  
 Указывает, что полоса является горизонтально или вертикально. `bHorz` Параметр имеет ненулевое значение, если панель горизонтальный и равно 0, если это вертикально.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Панель элементов управления размер в точках из `CSize` объекта.  
  
### <a name="remarks"></a>Примечания  
 Панели элементов управления, таких как панели инструментов можно растянуть по горизонтали или по вертикали для размещения кнопок из панели управления.  
  
 Если `bStretch` — **TRUE**, растянуть измерения вдоль ориентации, предоставляемые `bHorz`. Другими словами Если `bHorz` — **FALSE**, Панель растягивается по вертикали. Если `bStretch` — **FALSE**, происходит без растягивания. Ниже приведены возможные перестановки и полученный стилей панели элементов управления, из `bStretch` и `bHorz`.  
  
|bStretch|bHorz|Растяжение|Ориентация|Закрепление не закрепления|  
|--------------|-----------|----------------|-----------------|--------------------------|  
|**ЗНАЧЕНИЕ TRUE**|**ЗНАЧЕНИЕ TRUE**|Растяжение по горизонтали|Горизонтально|Не закрепления|  
|**ЗНАЧЕНИЕ TRUE**|**ЗНАЧЕНИЕ FALSE**|Растяжение по вертикали|Вертикально|Не закрепления|  
|**ЗНАЧЕНИЕ FALSE**|**ЗНАЧЕНИЕ TRUE**|Без растягивания доступны|Горизонтально|Закрепление|  
|**ЗНАЧЕНИЕ FALSE**|**ЗНАЧЕНИЕ FALSE**|Без растягивания доступны|Вертикально|Закрепление|  
  
##  <a name="a-namecalcinsiderecta--ccontrolbarcalcinsiderect"></a><a name="calcinsiderect"></a>CControlBar::CalcInsideRect  
 Платформа вызывает эту функцию для расчета клиентской области элемента панели управления.  
  
```  
virtual void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Содержит текущие размеры панели управления; включая границы.  
  
 `bHorz`  
 Указывает, что полоса является горизонтально или вертикально. `bHorz` Параметр имеет ненулевое значение, если панель горизонтальный и равно 0, если это вертикально.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается до рисования панели управления.  
  
 Переопределите эту функцию для настройки отображения границы и полосе захвата панели элементов управления.  
  
##  <a name="a-nameccontrolbara--ccontrolbarccontrolbar"></a><a name="ccontrolbar"></a>CControlBar::CControlBar  
 Создает объект `CControlBar`.  
  
```  
CControlBar();
```  
  
##  <a name="a-namedopainta--ccontrolbardopaint"></a><a name="dopaint"></a>CControlBar::DoPaint  
 Вызывается платформой для отображения границы и полосе захвата панели элементов управления.  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства, используемый для отрисовки границ и захвата панели элементов управления.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки поведения отрисовки панели элементов управления.  
  
 Другой способ настройки является переопределение `DrawBorders` и `DrawGripper` функции и добавьте пользовательский код рисования границ и захвата. Поскольку эти методы вызываются по умолчанию `DoPaint` метод, переопределенный `DoPaint` не требуется.  
  
##  <a name="a-namedrawbordersa--ccontrolbardrawborders"></a><a name="drawborders"></a>CControlBar::DrawBorders  
 Вызывается платформой для визуализации границ панели управления.  
  
```  
virtual void DrawBorders(
    CDC* pDC,  
    CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства, используемый для отрисовки границ панели управления.  
  
 `rect`  
 Объект `CRect` объект, содержащий размеры панели управления.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, чтобы настроить внешний вид границы панели управления.  
  
##  <a name="a-namedrawgrippera--ccontrolbardrawgripper"></a><a name="drawgripper"></a>CControlBar::DrawGripper  
 Вызывается платформой для отображения захвата панели управления.  
  
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
  
##  <a name="a-nameenabledockinga--ccontrolbarenabledocking"></a><a name="enabledocking"></a>CControlBar::EnableDocking  
 Эта функция вызывается для включения закреплять панели элементов управления.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDockStyle`  
 Указывает на панели управления, поддерживает ли закрепление, так и его родительского окна, к которому можно закрепить на панели управления, если поддерживается. Может иметь одно или несколько из следующих:  
  
- `CBRS_ALIGN_TOP`Позволяет закрепления в верхней части клиентской области.  
  
- `CBRS_ALIGN_BOTTOM`Позволяет закрепления в нижней части области клиента.  
  
- `CBRS_ALIGN_LEFT`Позволяет Закрепление левого края клиентской области.  
  
- `CBRS_ALIGN_RIGHT`Позволяет закрепления в правую часть клиентской области.  
  
- `CBRS_ALIGN_ANY`Позволяет в любой части клиентской области закрепления.  
  
- `CBRS_FLOAT_MULTI`Позволяет несколько панелей элементов управления к перемещению в окна одной области.  
  
 Если значение равно 0 (то есть, указывающее флаги не) панели управления не будет закреплен.  
  
### <a name="remarks"></a>Примечания  
 Указанных сторон должна соответствовать одной из сторон включено закрепление в фрейме окна назначения или нельзя закрепить панель элементов управления, окно.  
  
##  <a name="a-namegetbarstylea--ccontrolbargetbarstyle"></a><a name="getbarstyle"></a>CControlBar::GetBarStyle  
 Эта функция вызывается для определения того, какие **CBRS_** (стили панель управления) в настоящее время настроек панели управления.  
  
```  
DWORD GetBarStyle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий **CBRS_** параметры панели управления (Стили панели управления). В разделе [CControlBar::SetBarStyle](#setbarstyle) полный список доступных стилей.  
  
### <a name="remarks"></a>Примечания  
 Не обрабатывает **WS_** стили (стиль окна).  
  
##  <a name="a-namegetbordersa--ccontrolbargetborders"></a><a name="getborders"></a>CControlBar::GetBorders  
 Возвращает текущие значения границы панели управления.  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CRect` , содержащий текущей ширины (в пикселях) каждого края объекта панели управления. Например, значение `left` член из [CRect](../../atl-mfc-shared/reference/crect-class.md) , представляет ширину левой границы.  
  
##  <a name="a-namegetcounta--ccontrolbargetcount"></a><a name="getcount"></a>CControlBar::GetCount  
 Возвращает число не `HWND` элементам на `CControlBar` объект.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество отличных `HWND` элементам на `CControlBar` объект. Эта функция возвращает 0 для [CDialogBar](../../mfc/reference/cdialogbar-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Тип элемента зависит от производного объекта: области для [CStatusBar](../../mfc/reference/cstatusbar-class.md) объектов и кнопки и разделители для [CToolBar](../../mfc/reference/ctoolbar-class.md) объектов.  
  
##  <a name="a-namegetdockingframea--ccontrolbargetdockingframe"></a><a name="getdockingframe"></a>CControlBar::GetDockingFrame  
 Вызовите эту функцию-член для получения указателя в текущее окно фрейма, к которому прикреплено панели управления.  
  
```  
CFrameWnd* GetDockingFrame() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на фрейм окна, в случае успешного выполнения; в противном случае **NULL**.  
  
 Если панель элементов управления не закрепляются фрейма окна (Если панель элементов управления с плавающей запятой), эта функция возвращает указатель к родительскому [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md).  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о закрепляемых панелей см. в разделе [CControlBar::EnableDocking](#enabledocking) и [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).  
  
##  <a name="a-nameisfloatinga--ccontrolbarisfloating"></a><a name="isfloating"></a>CControlBar::IsFloating  
 Вызовите эту функцию-член для определения плавающая или закрепленная панели управления.  
  
```  
BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если панель элементов управления с плавающей запятой; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Чтобы изменить состояние панели элементов управления из закрепленного станет плавающим, следует вызвать [CFrameWnd::FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar).  
  
##  <a name="a-namembautodeletea--ccontrolbarmbautodelete"></a><a name="m_bautodelete"></a>CControlBar::m_bAutoDelete  
 Если значение ненулевое, `CControlBar` объект удаляется при удалении на панели управления Windows.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_bAutoDelete`— это открытая переменная типа **BOOL**.  
  
 Обычно объект панели элементов управления является встроенным в объекте фреймового окна. В этом случае `m_bAutoDelete` равно 0, поскольку объект embedded панель уничтожается при уничтожении окна фрейма.  
  
 Присвойте этой переменной значение ненулевое значение, если выделить `CControlBar` объектов в куче и вы не планируете вызвать **удаление**.  
  
##  <a name="a-namempinplaceownera--ccontrolbarmpinplaceowner"></a><a name="m_pinplaceowner"></a>CControlBar::m_pInPlaceOwner  
 Владелец на месте панели управления.  
  
```  
CWnd* m_pInPlaceOwner;  
```  
  
##  <a name="a-nameonupdatecmduia--ccontrolbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CControlBar::OnUpdateCmdUI  
 Эта функция-член вызывается платформой для обновления состояния панели инструментов или состояния.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 `pTarget`  
 Указатель фрейма главного окна приложения. Этот указатель используется для маршрутизации сообщений.  
  
 `bDisableIfNoHndler`  
 Флаг, указывающий, должен ли элемент управления, который не имеет обновления обработчика автоматически отображается как отключенные.  
  
### <a name="remarks"></a>Примечания  
 Чтобы обновить отдельные кнопки или области, используйте `ON_UPDATE_COMMAND_UI` макрос на карте сообщения, чтобы правильно настроить обработчик. В разделе [ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4) Дополнительные сведения об использовании этого макроса.  
  
 `OnUpdateCmdUI`Вызывается средой во время простоя приложения. Окна фрейма обновления должны иметь дочернего окна, по крайней мере косвенно отображается окно. `OnUpdateCmdUI`существует расширенная переопределяемыми.  
  
##  <a name="a-namesetbarstylea--ccontrolbarsetbarstyle"></a><a name="setbarstyle"></a>CControlBar::SetBarStyle  
 Эта функция вызывается для задайте требуемую **CBRS_** стилей для панели управления.  
  
```  
void SetBarStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Нужные стили панели управления. Может иметь одно или несколько из следующих:  
  
- `CBRS_ALIGN_TOP`Позволяет панели управления закреплено в верхней части клиентской области окна фрейма.  
  
- `CBRS_ALIGN_BOTTOM`Позволяет панели управления закреплено в нижнюю часть клиентской области окна фрейма.  
  
- `CBRS_ALIGN_LEFT`Позволяет панели управления, чтобы закрепить левого края клиентской области окна фрейма.  
  
- `CBRS_ALIGN_RIGHT`Позволяет панели управления, чтобы прикрепить к правой части клиентской области окна фрейма.  
  
- `CBRS_ALIGN_ANY`Позволяет панели управления, чтобы закрепить с любой стороны клиентской области окна фрейма.  
  
- `CBRS_BORDER_TOP`В результате границы рисуемого верхнего края панели элементов управления, на которые будет видимым.  
  
- `CBRS_BORDER_BOTTOM`В результате границы, отображаемый на нижней границе панели элементов управления, на которые будет видимым.  
  
- `CBRS_BORDER_LEFT`В результате границы рисуемого в левой панели элементов управления, на которые будет видимым.  
  
- `CBRS_BORDER_RIGHT`В результате границы, отображаемый на правой стороне панели элементов управления, на которые будет видимым.  
  
- `CBRS_FLOAT_MULTI`Позволяет несколько панелей элементов управления к перемещению в окна одной области.  
  
- `CBRS_TOOLTIPS`В результате всплывающие подсказки, отображаемый для панели управления.  
  
- `CBRS_FLYBY`Устанавливает для текста сообщения обновляемых одновременно и всплывающие подсказки.  
  
- **CBRS_GRIPPER** вызывает захвата, аналогичного используемому полосами в **CReBar** объекта, отображаемый для любого `CControlBar`-производного класса.  
  
### <a name="remarks"></a>Примечания  
 Не влияет на **WS_** параметры (стиль окна).  
  
##  <a name="a-namesetbordersa--ccontrolbarsetborders"></a><a name="setborders"></a>CControlBar::SetBorders  
 Вызывайте эту функцию, чтобы задать размер границы панели управления.  
  
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
 Ширина правой границы панели управления (в пикселях).  
  
 *cyBottom*  
 Высота (в пикселях) панели управления нижней границы.  
  
 `lpRect`  
 Указатель на [CRect](../../atl-mfc-shared/reference/crect-class.md) объект, содержащий текущий ширину (в пикселях) границы каждого объекта панели управления.  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает левой и правой границ и верхней и нижней границ панели управления на 5 пикселей до 2 пикселей:  
  
 [!code-cpp[NVC_MFCControlLadenDialog&#61;](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]  
  
##  <a name="a-namesetinplaceownera--ccontrolbarsetinplaceowner"></a><a name="setinplaceowner"></a>CControlBar::SetInPlaceOwner  
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
 [CReBar-класс](../../mfc/reference/crebar-class.md)

