---
title: Класс CControlBar | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CControlBar [MFC], CControlBar
- CControlBar [MFC], CalcDynamicLayout
- CControlBar [MFC], CalcFixedLayout
- CControlBar [MFC], CalcInsideRect
- CControlBar [MFC], DoPaint
- CControlBar [MFC], DrawBorders
- CControlBar [MFC], DrawGripper
- CControlBar [MFC], EnableDocking
- CControlBar [MFC], GetBarStyle
- CControlBar [MFC], GetBorders
- CControlBar [MFC], GetCount
- CControlBar [MFC], GetDockingFrame
- CControlBar [MFC], IsFloating
- CControlBar [MFC], OnUpdateCmdUI
- CControlBar [MFC], SetBarStyle
- CControlBar [MFC], SetBorders
- CControlBar [MFC], SetInPlaceOwner
- CControlBar [MFC], m_bAutoDelete
- CControlBar [MFC], m_pInPlaceOwner
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8520b119d2e40ceb1261e4a08727df8880c906b8
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336928"
---
# <a name="ccontrolbar-class"></a>CControlBar Class
Базовый класс для классов панелей элементов управления [CStatusBar](../../mfc/reference/cstatusbar-class.md), [CToolBar](../../mfc/reference/ctoolbar-class.md), [CDialogBar](../../mfc/reference/cdialogbar-class.md), [CReBar](../../mfc/reference/crebar-class.md), и [ COleResizeBar](../../mfc/reference/coleresizebar-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CControlBar : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CControlBar::CControlBar](#ccontrolbar)|Создает объект `CControlBar`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CControlBar::CalcDynamicLayout](#calcdynamiclayout)|Возвращает размер панели динамических элементов управления как [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.|  
|[CControlBar::CalcFixedLayout](#calcfixedlayout)|Возвращает размер панели элементов управления, как [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.|  
|[CControlBar::CalcInsideRect](#calcinsiderect)|Возвращает текущий размеры области элемента управления; включая границы.|  
|[CControlBar::DoPaint](#dopaint)|Отображает границы и полосы захвата панели элементов управления.|  
|[CControlBar::DrawBorders](#drawborders)|Выполняет визуализацию границ элемента панели элементов управления.|  
|[CControlBar::DrawGripper](#drawgripper)|Отрисовывает границу панели элементов управления.|  
|[CControlBar::EnableDocking](#enabledocking)|Позволяет на панели элементов управления быть закрепленными или с плавающей запятой.|  
|[CControlBar::GetBarStyle](#getbarstyle)|Извлекает параметры стиля элемента управления панели.|  
|[CControlBar::GetBorders](#getborders)|Получает значения границы панели элементов управления.|  
|[CControlBar::GetCount](#getcount)|Возвращает количество элементов, отличных от HWND в панели управления.|  
|[CControlBar::GetDockingFrame](#getdockingframe)|Возвращает указатель на кадр, к которой закрепляется на панели элементов управления.|  
|[CControlBar::IsFloating](#isfloating)|Возвращает ненулевое значение, если на панели управления с плавающей запятой панель элементов управления.|  
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|Вызывает обработчики команд пользовательского интерфейса.|  
|[CControlBar::SetBarStyle](#setbarstyle)|Изменяет параметры стиля элемента управления панели.|  
|[CControlBar::SetBorders](#setborders)|Задает значения границы панели элементов управления.|  
|[CControlBar::SetInPlaceOwner](#setinplaceowner)|Изменяет владельца на месте на панели элементов управления.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CControlBar::m_bAutoDelete](#m_bautodelete)|Если значение ненулевое, `CControlBar` объект удаляется при удалении панели элементов управления Windows.|  
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|Владелец на месте на панели управления.|  
  
## <a name="remarks"></a>Примечания  
 Панель элементов управления — это окно, которое обычно выравнивается слева или справа от окна фрейма. Он может содержать дочерние элементы, находящиеся на основе HWND элементов управления, которые представляют собой окна, формирующие и отвечать на сообщения Windows или HWND основанным элементы, которые не являются windows и управляются код приложения или код платформы. Списки и элементы управления редактирования являются примерами элементов управления на основе HWND; панели строки состояния и кнопками с точечными рисунками являются примерами элементов управления, не основанного HWND.  
  
 Панель элементов управления windows обычно являются дочерними окнами родительское окно фрейма и обычно имеют элементов с общим родителем для представления клиента или клиент MDI фрейма окна. Объект `CControlBar` объект использует сведения о клиентской прямоугольной области родительского окна для размещения себя. Оповещает родительского окна о том, сколько места остается нераспределенного в клиентской области родительского окна.  
  
 Дополнительные сведения о `CControlBar`, см. в разделе:  
  
- [Панели элементов управления](../../mfc/control-bars.md)  
  
- [Техническое Примечание 31: Панелей элементов управления](../../mfc/tn031-control-bars.md).  
  
-   Статье базы знаний Q242577: PRB: обновление команды пользовательского интерфейса обработчики не работают для вложенных меню в диалоговое окно  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CControlBar`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxext.h  
  
##  <a name="calcdynamiclayout"></a>  CControlBar::CalcDynamicLayout  
 Платформа вызывает эту функцию-член для вычисления размеров динамическую панель инструментов.  
  
```  
virtual CSize CalcDynamicLayout(
    int nLength,  
    DWORD nMode);
```  
  
### <a name="parameters"></a>Параметры  
 *nLength*  
 Запрошенный размер на панели управления горизонтальной или вертикальной, в зависимости от *dwMode*.  
  
 *nMode*  
 Далее перечислены стандартные флаги используются для определения высоту и ширину панели динамических элементов управления. Использование побитового или (&#124;) оператор для объединения флагов.  
  
|Флаги режима макета|Что означает|  
|-----------------------|-------------------|  
|LM_STRETCH|Указывает, должен быть растянут на панели управления, размер кадра. Набор, если панель не закрепляемую панель, (недоступно для закрепления). Не группе при закрепленной панели или с плавающей запятой (доступно для закрепления). Если задано, LM_STRETCH игнорирует *nLength* и возвращает измерения, на основе состояния LM_HORZ. Так же, как работает LM_STRETCH *bStretch* параметр, используемый в [CalcFixedLayout](#calcfixedlayout); см. Дополнительные сведения о связи между растягивания и ориентации этой функции-члена.|  
|LM_HORZ|Указывает, что полоса становится горизонтальной или вертикальной. Задайте, если строке его компонент ориентирован горизонтально и вертикально, если оно не задано. Так же, как работает LM_HORZ *bHorz* параметр, используемый в [CalcFixedLayout](#calcfixedlayout); см. Дополнительные сведения о связи между растягивания и ориентации этой функции-члена.|  
|LM_MRUWIDTH|Недавно использовавшиеся динамическую ширину. Игнорирует *nLength* параметра и с помощью сохраненных самые последние использовавшиеся ширины.|  
|LM_HORZDOCK|Горизонтальный закреплено измерений. Игнорирует *nLength* параметр и возвращает динамический размер с наибольшей шириной.|  
|LM_VERTDOCK|Вертикальный закреплено измерений. Игнорирует *nLength* параметр и возвращает динамический размер наибольшего высоты.|  
|LM_LENGTHY|Если *nLength* указывающее высоту (оси Y) вместо ширины.|  
|LM_COMMIT|Сбрасывает LM_MRUWIDTH текущей ширины плавающей панели элементов управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 На панели управления размер в пикселях из [CSize](../../atl-mfc-shared/reference/csize-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член для предоставления собственных динамического макета в классах, производных от переопределения `CControlBar`. Классы MFC, производные от `CControlBar`, такие как [CToolbar](../../mfc/reference/ctoolbar-class.md), переопределите эту функцию-член и предоставлять собственную реализацию.  
  
##  <a name="calcfixedlayout"></a>  CControlBar::CalcFixedLayout  
 Вызовите эту функцию-член для вычисления горизонтальный размер окна панели элементов управления.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры  
 *bStretch*  
 Указывает, должен быть растянут панели, размер кадра. *BStretch* параметр имеет ненулевое значение, если панели не закрепляемую панель, (недоступно для закрепления) и доступна 0 при закрепленными или с плавающей запятой (закрепления).  
  
 *bHorz*  
 Указывает, что полоса становится горизонтальной или вертикальной. *BHorz* параметр имеет ненулевое значение, если в строке его компонент ориентирован горизонтально и равно 0, если он его компонент ориентирован вертикально.  
  
### <a name="return-value"></a>Возвращаемое значение  
 На панели управления размер в пикселях из `CSize` объекта.  
  
### <a name="remarks"></a>Примечания  
 Панели элементов управления, таких как панели инструментов можно растянуть по горизонтали или по вертикали для размещения кнопок содержащихся в панели управления.  
  
 Если *bStretch* имеет значение TRUE, растянуть измерения вдоль ориентацию, предоставляемые *bHorz*. Другими словами Если *bHorz* имеет значение FALSE, на панели управления растягивается по вертикали. Если *bStretch* имеет значение FALSE, происходит не stretch. Ниже приведены возможные перестановки и итоговый стили панель элементов управления, из *bStretch* и *bHorz*.  
  
|bStretch|bHorz|Растяжение|Ориентация|Закрепление или не закрепления|  
|--------------|-----------|----------------|-----------------|--------------------------|  
|true|true|Растяжение по горизонтали|Горизонтально|Не закрепления|  
|true|false|Растяжение по вертикали|Вертикально|Не закрепления|  
|false|true|Без растягивания доступных|Горизонтально|Закрепление|  
|false|false|Без растягивания доступных|Вертикально|Закрепление|  
  
##  <a name="calcinsiderect"></a>  CControlBar::CalcInsideRect  
 Платформа вызывает эту функцию для расчета клиентской области панели элементов управления.  
  
```  
virtual void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *Rect*  
 Содержит текущие размеры панели элементов управления; включая границы.  
  
 *bHorz*  
 Указывает, что полоса становится горизонтальной или вертикальной. *BHorz* параметр имеет ненулевое значение, если в строке его компонент ориентирован горизонтально и равно 0, если он его компонент ориентирован вертикально.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается до рисования панели элементов управления.  
  
 Переопределите эту функцию для настройки оформления, границы и полосы захвата на панели управления.  
  
##  <a name="ccontrolbar"></a>  CControlBar::CControlBar  
 Создает объект `CControlBar`.  
  
```  
CControlBar();
```  
  
##  <a name="dopaint"></a>  CControlBar::DoPaint  
 Вызывается платформой для отрисовки границ и полосы захвата на панели управления.  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 *основного контроллера домена*  
 Указывает контекст устройства, используемого для отрисовки границ и захвата панели элементов управления.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки поведения рисования панели элементов управления.  
  
 Другой способ настройки заключается в Переопределите `DrawBorders` и `DrawGripper` функции и добавьте пользовательский код рисования для границы и полосы захвата. Так как эти методы вызываются по умолчанию `DoPaint` метод, переопределенный `DoPaint` не требуется.  
  
##  <a name="drawborders"></a>  CControlBar::DrawBorders  
 Вызывается платформой для отрисовки границ элемента панели элементов управления.  
  
```  
virtual void DrawBorders(
    CDC* pDC,  
    CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 *основного контроллера домена*  
 Указывает контекст устройства, используемого для отрисовки границ элемента панели элементов управления.  
  
 *Rect*  
 Объект `CRect` объект, содержащий размеры панели элементов управления.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, чтобы настроить внешний вид границы панели управления.  
  
##  <a name="drawgripper"></a>  CControlBar::DrawGripper  
 Вызывается платформой для отрисовки захвата на панели управления.  
  
```  
virtual void DrawGripper(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 *основного контроллера домена*  
 Указывает контекст устройства, используемого для отрисовки захвата панели управления.  
  
 *Rect*  
 Объект `CRect` объект, содержащий размеры захвата панели управления.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки внешнего вида границу панели управления.  
  
##  <a name="enabledocking"></a>  CControlBar::EnableDocking  
 Вызывайте эту функцию, чтобы быть закреплено на панели элементов управления.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDockStyle*  
 Указывает на панели управления, поддерживает ли закрепления и ее краями его родительского окна, к которому могут быть закреплены на панели управления, если поддерживается. Может иметь одно или несколько из следующих:  
  
- CBRS_ALIGN_TOP позволяет закрепления в верхней части клиентской области.  
  
- CBRS_ALIGN_BOTTOM позволяет закрепления в нижней части клиентской области.  
  
- CBRS_ALIGN_LEFT позволяет Закрепление левого края клиентской области.  
  
- CBRS_ALIGN_RIGHT позволяет закрепления справа от клиентской области.  
  
- CBRS_ALIGN_ANY позволяет в любой части клиентской области закрепления.  
  
- CBRS_FLOAT_MULTI позволяет несколько панелей элементов управления оставить плавающим, в окне одной области.  
  
 Если значение равно 0 (то есть, указывающее флаги не) на панели управления не будет прикреплена.  
  
### <a name="remarks"></a>Примечания  
 Указанных сторон должно соответствовать одной из сторон включено закрепление целевой фрейм окна, или не может быть закреплено на панели управления для этого фрейма окна.  
  
##  <a name="getbarstyle"></a>  CControlBar::GetBarStyle  
 Вызывайте эту функцию, чтобы определить, какие **CBRS_** параметры (стили полосы управления) в настоящее время заданы для панели элементов управления.  
  
```  
DWORD GetBarStyle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий **CBRS_** (стили элемента управления полосы) параметры панели управления. См. в разделе [CControlBar::SetBarStyle](#setbarstyle) полный список доступных стилей.  
  
### <a name="remarks"></a>Примечания  
 Не обрабатывает **WS_** стили (стиль окна).  
  
##  <a name="getborders"></a>  CControlBar::GetBorders  
 Возвращает текущие значения границы для панели элементов управления.  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CRect` , содержащий текущую ширину каждого края объекта панели элементов управления (в пикселях). Например, значение *левой* член из [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта, ширину левой границы.  
  
##  <a name="getcount"></a>  CControlBar::GetCount  
 Возвращает количество элементов, отличных от HWND на `CControlBar` объекта.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов не HWND на `CControlBar` объекта. Эта функция возвращает 0 для [CDialogBar](../../mfc/reference/cdialogbar-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Тип элемента зависит от производного объекта: области для [CStatusBar](../../mfc/reference/cstatusbar-class.md) объектов и кнопки и разделители для [CToolBar](../../mfc/reference/ctoolbar-class.md) объектов.  
  
##  <a name="getdockingframe"></a>  CControlBar::GetDockingFrame  
 Вызывайте эту функцию члена, чтобы получить указатель на текущее окно фрейма, к которому закрепленной панели управления.  
  
```  
CFrameWnd* GetDockingFrame() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на окно, если выполнение прошло успешно; в противном случае имеет значение NULL.  
  
 Если панель элементов управления не прикреплен к окна фрейма (то есть, если панель элементов управления с плавающей запятой), эта функция возвращает указатель к родительскому [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md).  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о закрепляемых панелей, см. в разделе [CControlBar::EnableDocking](#enabledocking) и [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).  
  
##  <a name="isfloating"></a>  CControlBar::IsFloating  
 Вызовите для определения, является ли панель элементов управления плавающая или закрепленная эта функция-член.  
  
```  
BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если панель элементов управления с плавающей запятой; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Чтобы изменить состояние на панели элементов управления из закреплено с плавающей запятой, следует вызвать [CFrameWnd::FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar).  
  
##  <a name="m_bautodelete"></a>  CControlBar::m_bAutoDelete  
 Если значение ненулевое, `CControlBar` объект удаляется при удалении панели элементов управления Windows.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Примечания  
 *m_bAutoDelete* — это открытая переменная типа BOOL.  
  
 Объект панели управления, обычно является встроенным в объекте окна фрейма. В этом случае *m_bAutoDelete* равно 0, так как объект внедренных панелей элементов управления уничтожается при уничтожении окна фрейма.  
  
 Присвойте этой переменной значение ненулевое значение, если выделить `CControlBar` объект в куче и вы не планируете вызвать **удалить**.  
  
##  <a name="m_pinplaceowner"></a>  CControlBar::m_pInPlaceOwner  
 Владелец на месте на панели управления.  
  
```  
CWnd* m_pInPlaceOwner;  
```  
  
##  <a name="onupdatecmdui"></a>  CControlBar::OnUpdateCmdUI  
 Эта функция-член вызывается платформой для обновления статуса панели инструментов или состояние строки.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 *pTarget*  
 Указывает фрейма главного окна приложения. Этот указатель используется для маршрутизации сообщений обновления.  
  
 *bDisableIfNoHndler*  
 Флаг, указывающий, должен ли элемент управления, который не имеет обновление обработчика автоматически отображается как отключенная.  
  
### <a name="remarks"></a>Примечания  
 Для обновления отдельных кнопки или области, используйте макрос ON_UPDATE_COMMAND_UI в схему сообщений соответствующим образом задать обработчика обновлений. См. в разделе [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) Дополнительные сведения об использовании этого макроса.  
  
 `OnUpdateCmdUI` вызывается платформой, когда приложение бездействует. Окна фрейма обновления должны иметь дочернее окно, по крайней мере косвенно видимым окно. `OnUpdateCmdUI` — Это усовершенствованное переопределяемый.  
  
##  <a name="setbarstyle"></a>  CControlBar::SetBarStyle  
 Вызывайте эту функцию, чтобы задать нужный **CBRS_** стилей для панели элементов управления.  
  
```  
void SetBarStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 *dwStyle*  
 Нужные стили для панели элементов управления. Может иметь одно или несколько из следующих:  
  
- CBRS_ALIGN_TOP позволяет прикреплять к верхней части клиентской области окна фрейма панели элементов управления.  
  
- CBRS_ALIGN_BOTTOM позволяет прикреплять к нижней части клиентской области окна фрейма панели элементов управления.  
  
- CBRS_ALIGN_LEFT позволяет прикреплять к левой части клиентской области окна фрейма панели элементов управления.  
  
- CBRS_ALIGN_RIGHT позволяет прикреплять к правой части клиентской области окна фрейма панели элементов управления.  
  
- CBRS_ALIGN_ANY позволяет прикреплять к любой части клиентской области окна фрейма панели элементов управления.  
  
- CBRS_BORDER_TOP вызывает границы для отображения верхнего края элемента управления панели, когда она будет видима.  
  
- CBRS_BORDER_BOTTOM вызывает границы для отрисовки для нижней границы элемента управления панели, когда она будет видима.  
  
- CBRS_BORDER_LEFT вызывает границы для отрисовки у левого края элемента управления панели, когда она будет видима.  
  
- CBRS_BORDER_RIGHT вызывает границы для отрисовки на правой стороне элемента управления панели, когда она будет видима.  
  
- CBRS_FLOAT_MULTI позволяет несколько панелей элементов управления оставить плавающим, в окне одной области.  
  
- CBRS_TOOLTIPS вызывает всплывающие подсказки для панели элементов управления.  
  
- CBRS_FLYBY вызывает текст сообщения обновления в то же время, как всплывающие подсказки.  
  
- CBRS_GRIPPER вызывает захвата, аналогичного используемому полосами в в `CReBar` объект, для отрисовки для любого `CControlBar`-производного класса.  
  
### <a name="remarks"></a>Примечания  
 Не влияет на **WS_** параметры (стиль окна).  
  
##  <a name="setborders"></a>  CControlBar::SetBorders  
 Вызывайте эту функцию, чтобы задать размер границ панели элементов управления.  
  
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
 Ширина (в пикселях) левой границы панели элементов управления.  
  
 *cyTop*  
 Высота (в пикселях) верхней границы панели элементов управления.  
  
 *cxRight*  
 Ширина правой границы панели элементов управления (в пикселях).  
  
 *cyBottom*  
 Высота (в пикселях) нижней границы панели элементов управления.  
  
 *lpRect*  
 Указатель на [CRect](../../atl-mfc-shared/reference/crect-class.md) , содержащий текущую ширину каждой границы объекта панели элементов управления (в пикселях).  
  
### <a name="example"></a>Пример  
 В следующем примере кода устанавливает верхней и нижней границ панели элементов управления 5 пикселей и левую и правую границы 2 пикселя:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#61](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]  
  
##  <a name="setinplaceowner"></a>  CControlBar::SetInPlaceOwner  
 Изменяет владельца на месте на панели элементов управления.  
  
```  
void SetInPlaceOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Указатель на объект `CWnd`.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CTRLBARS](../../visual-cpp-samples.md)   
 [Класс CWnd](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CToolBar](../../mfc/reference/ctoolbar-class.md)   
 [Класс CDialogBar](../../mfc/reference/cdialogbar-class.md)   
 [Класс CStatusBar](../../mfc/reference/cstatusbar-class.md)   
 [Класс CReBar](../../mfc/reference/crebar-class.md)
