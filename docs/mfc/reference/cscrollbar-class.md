---
title: "Класс CScrollBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CScrollBar
- AFXWIN/CScrollBar
- AFXWIN/CScrollBar::CScrollBar
- AFXWIN/CScrollBar::Create
- AFXWIN/CScrollBar::EnableScrollBar
- AFXWIN/CScrollBar::GetScrollBarInfo
- AFXWIN/CScrollBar::GetScrollInfo
- AFXWIN/CScrollBar::GetScrollLimit
- AFXWIN/CScrollBar::GetScrollPos
- AFXWIN/CScrollBar::GetScrollRange
- AFXWIN/CScrollBar::SetScrollInfo
- AFXWIN/CScrollBar::SetScrollPos
- AFXWIN/CScrollBar::SetScrollRange
- AFXWIN/CScrollBar::ShowScrollBar
dev_langs:
- C++
helpviewer_keywords:
- CScrollBar [MFC], CScrollBar
- CScrollBar [MFC], Create
- CScrollBar [MFC], EnableScrollBar
- CScrollBar [MFC], GetScrollBarInfo
- CScrollBar [MFC], GetScrollInfo
- CScrollBar [MFC], GetScrollLimit
- CScrollBar [MFC], GetScrollPos
- CScrollBar [MFC], GetScrollRange
- CScrollBar [MFC], SetScrollInfo
- CScrollBar [MFC], SetScrollPos
- CScrollBar [MFC], SetScrollRange
- CScrollBar [MFC], ShowScrollBar
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d458fe5f7bcaf25fc5bb0685bb382a72d44d183
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cscrollbar-class"></a>Класс CScrollBar
Предоставляет функции элемента управления полосой прокрутки Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CScrollBar : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CScrollBar::CScrollBar](#cscrollbar)|Создает объект `CScrollBar`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CScrollBar::Create](#create)|Создает полосой прокрутки Windows и прикрепляет его к `CScrollBar` объекта.|  
|[CScrollBar::EnableScrollBar](#enablescrollbar)|Включает или выключает одну или обе стрелки полосы прокрутки.|  
|[CScrollBar::GetScrollBarInfo](#getscrollbarinfo)|Извлекает сведения о полосы с помощью прокрутки `SCROLLBARINFO` структуры.|  
|[CScrollBar::GetScrollInfo](#getscrollinfo)|Извлекает сведения о полосе прокрутки.|  
|[CScrollBar::GetScrollLimit](#getscrolllimit)|Извлекает ограничение полосы прокрутки|  
|[CScrollBar::GetScrollPos](#getscrollpos)|Извлекает текущее положение ползунка.|  
|[CScrollBar::GetScrollRange](#getscrollrange)|Возвращает значение текущей позиции минимальную и максимальную полосу прокрутки для указанной полосы прокрутки.|  
|[CScrollBar::SetScrollInfo](#setscrollinfo)|Задает сведения о полосе прокрутки.|  
|[CScrollBar::SetScrollPos](#setscrollpos)|Задает текущее положение ползунка.|  
|[CScrollBar::SetScrollRange](#setscrollrange)|Задает для указанной полосы прокрутки положения минимума и максимума.|  
|[CScrollBar::ShowScrollBar](#showscrollbar)|Показывает или скрывает полосу прокрутки.|  
  
## <a name="remarks"></a>Примечания  
 Создание элемента управления полосы прокрутки в два этапа. Во-первых, вызовите конструктор `CScrollBar` для создания `CScrollBar` объекта, а затем вызвать [создать](#create) функции-члена для создания элемента управления полосой прокрутки Windows и присоединить его к `CScrollBar` объекта.  
  
 Если вы создаете `CScrollBar` объектов в диалоговом окне (с помощью ресурса диалогового окна) `CScrollBar` автоматически освобождается, когда пользователь закрывает диалоговое окно.  
  
 Если вы создаете `CScrollBar` объекта в окне, может потребоваться удалить его.  
  
 Если вы создаете `CScrollBar` объекта в стеке, удаляется автоматически. При создании `CScrollBar` объекта в куче с помощью **новый** функции, необходимо вызвать **удаление** для объекта, чтобы уничтожить его, когда пользователь закроет полосой прокрутки Windows.  
  
 Если выделять память в `CScrollBar` объекта, переопределите `CScrollBar` деструктор для удаления распределения.  
  
 Дополнительные сведения об использовании `CScrollBar`, в разделе [элементов управления](../../mfc/controls-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CScrollBar`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="create"></a>CScrollBar::Create  
 Создает полосой прокрутки Windows и прикрепляет его к `CScrollBar` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Указывает прокрутку стиль линейки. Примените любое сочетание [стили полосы прокрутки](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles) полосу прокрутки.  
  
 `rect`  
 Указывает размер полосы прокрутки и позиции. Может быть как `RECT` структуры или `CRect` объекта.  
  
 `pParentWnd`  
 Указывает прокрутку линейки родительского окна, обычно `CDialog` объекта. Он не должен быть **NULL**.  
  
 `nID`  
 Идентификатор элемента управления полосы прокрутки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CScrollBar` объекта в два этапа. Во-первых, вызывает конструктор, который создает `CScrollBar` объекта; затем вызвать **создать**, который создает и инициализирует полосу прокрутки связанного Windows и прикрепляет его к `CScrollBar` объекта.  
  
 Применить следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) полосу прокрутки:  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
- **WS_GROUP** для группировки элементов управления  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]  
  
##  <a name="cscrollbar"></a>CScrollBar::CScrollBar  
 Создает объект `CScrollBar`.  
  
```  
CScrollBar();
```  
  
### <a name="remarks"></a>Примечания  
 После создания объекта, вызовите метод **создать** функции-члена для создания и инициализации полосой прокрутки Windows.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]  
  
##  <a name="enablescrollbar"></a>CScrollBar::EnableScrollBar  
 Включает или выключает одну или обе стрелки полосы прокрутки.  
  
```  
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```  
  
### <a name="parameters"></a>Параметры  
 `nArrowFlags`  
 Указывает ли стрелками включены или отключены и какие стрелки включены или отключены. Этот параметр может принимать одно из следующих значений:  
  
- **ESB_ENABLE_BOTH** позволяет обе стрелки полосы прокрутки.  
  
- **ESB_DISABLE_LTUP** отключает стрелку влево для горизонтальной полосы прокрутки или со стрелкой вверх для вертикальной полосы прокрутки.  
  
- **ESB_DISABLE_RTDN** отключает со стрелкой вправо для горизонтальной полосы прокрутки или стрелку вниз для вертикальной полосы прокрутки.  
  
- **ESB_DISABLE_BOTH** отключает обе стрелки полосы прокрутки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если включены или отключены в соответствии; стрелки в противном случае значение 0, означающее, что стрелки уже запрошенное состояние или произошла ошибка.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CScrollBar::SetScrollRange](#setscrollrange).  
  
##  <a name="getscrollbarinfo"></a>CScrollBar::GetScrollBarInfo  
 Возвращает сведения, **SCROLLBARINFO** структура поддерживает о полосе прокрутки.  
  
```  
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *pScrollInfo*  
 Указатель на [SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787535) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [SBM_SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787545) сообщения, как описано в Windows SDK.  
  
##  <a name="getscrollinfo"></a>CScrollBar::GetScrollInfo  
 Извлекает данные о полосе прокрутки, содержащиеся в структуре `SCROLLINFO`.  
  
```  
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,  
    UINT nMask = SIF_ALL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpScrollInfo`  
 Указатель на [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) структуры. См. в Windows SDK, Дополнительные сведения об этой структуры.  
  
 `nMask`  
 Указывает параметры панели прокрутки для извлечения. Типичное использование SIF_ALL, задает сочетание SIF_PAGE, SIF_POS, SIF_TRACKPOS и SIF_RANGE. В разделе `SCROLLINFO` Дополнительные сведения о значениях nMask.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если сообщение извлечено все значения, возвращается **TRUE**. В противном случае это **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 `GetScrollInfo`позволяет приложениям использовать позиции прокрутки 32-разрядной.  
  
 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) структура содержит сведения о полосы прокрутки, включая минимальной и максимальной прокрутки позиций, размер страницы и положение полосы прокрутки (бегунком). В разделе `SCROLLINFO` раздел структуры в Windows SDK, Дополнительные сведения об изменении структуры значения по умолчанию.  
  
 Обработчики, которые указывают на расположение полосы прокрутки, сообщения MFC Windows [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) и [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll), предоставляют только 16 бит данных позиции. `GetScrollInfo`и `SetScrollInfo` предоставляют 32 бита полосы данных позиции прокрутки. Таким образом, приложение может вызвать `GetScrollInfo` при обработке либо `CWnd::OnHScroll` или `CWnd::OnVScroll` для получения данных позиции прокрутки 32-разрядной панели.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrolllimit"></a>CScrollBar::GetScrollLimit  
 Получает максимально прокрутки положение полосы прокрутки.  
  
```  
int GetScrollLimit();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указывает положение полосы прокрутки в случае успешного выполнения; в противном случае — 0.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrollpos"></a>CScrollBar::GetScrollPos  
 Извлекает текущее положение ползунка.  
  
```  
int GetScrollPos() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Задает текущее положение ползунка в случае успешного выполнения; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Текущая позиция имеет относительное значение, от которого зависит текущий диапазон прокрутки. Например если полосы прокрутки находится в середине полоса прокрутки диапазон — от 100 до 200, текущая позиция — 150.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrollrange"></a>CScrollBar::GetScrollRange  
 Копирует текущие минимальное и максимальное полосы прокрутки положения указанной полосы прокрутки в расположениях, указанных в `lpMinPos` и `lpMaxPos`.  
  
```  
void GetScrollRange(
    LPINT lpMinPos,  
    LPINT lpMaxPos) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpMinPos`  
 Указывает целочисленной переменной, получающего положение минимума.  
  
 `lpMaxPos`  
 Указывает, получающего положение целочисленной переменной.  
  
### <a name="remarks"></a>Примечания  
 Диапазон по умолчанию для управления полосой прокрутки пуст (оба значения равны 0).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="setscrollinfo"></a>CScrollBar::SetScrollInfo  
 Задает сведения, `SCROLLINFO` структура поддерживает о полосе прокрутки.  
  
```  
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `lpScrollInfo`  
 Указатель на [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) структуры.  
  
 `bRedraw`  
 Указывает, следует ли заново полосу прокрутки, с учетом новых данных. Если `bRedraw` — **TRUE**, перерисовке полосы прокрутки. Если это **FALSE**, не перерисовке. По умолчанию перерисовке полосы прокрутки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении возвращается **TRUE**. В противном случае это **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Необходимо указать значения, необходимые для `SCROLLINFO` структуру параметров, включая значения флага.  
  
 `SCROLLINFO` Структура содержит сведения о полосы прокрутки, включая минимальной и максимальной прокрутки позиций, размер страницы и положение полосы прокрутки (бегунком). В разделе [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) раздел структуры в Windows SDK, Дополнительные сведения об изменении структуры значения по умолчанию.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]  
  
##  <a name="setscrollpos"></a>CScrollBar::SetScrollPos  
 Задает текущее положение ползунка значению, указанному `nPos` и, если указано, перерисовывает полосу прокрутки, чтобы отразить новое место.  
  
```  
int SetScrollPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Задает новое положение полосы прокрутки. Оно должно находиться в диапазоне прокрутки.  
  
 `bRedraw`  
 Указывает, следует ли заново полосу прокрутки, с учетом новой позиции. Если `bRedraw` — **TRUE**, перерисовке полосы прокрутки. Если это **FALSE**, не перерисовке. По умолчанию перерисовке полосы прокрутки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Задает предыдущих положение полосы прокрутки в случае успешного выполнения; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Задать `bRedraw` для **FALSE** каждый раз, когда полоса прокрутки перерисовывается при последующих вызовах в другую функцию, чтобы избежать необходимости полосы прокрутки, перерисовке дважды в течение более короткий интервал.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CScrollBar::SetScrollRange](#setscrollrange).  
  
##  <a name="setscrollrange"></a>CScrollBar::SetScrollRange  
 Задает для указанной полосы прокрутки положения минимума и максимума.  
  
```  
void SetScrollRange(
    int nMinPos,  
    int nMaxPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nMinPos`  
 Задает минимальные позиции прокрутки.  
  
 `nMaxPos`  
 Указывает максимальное позиции прокрутки.  
  
 `bRedraw`  
 Указывает, является ли полоса прокрутки необходимости перерисовки в соответствии с изменениями. Если `bRedraw` — **TRUE**, перерисовке полосы прокрутки; Если **FALSE**, не перерисовке. Перерисовке по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Задать `nMinPos` и `nMaxPos` 0, чтобы скрыть полосы прокрутки standard.  
  
 Не вызывайте эту функцию, чтобы скрыть полосу прокрутки при обработке сообщения уведомления полосы прокрутки.  
  
 Если вызов `SetScrollRange` сразу за вызов `SetScrollPos` функция-член, установите `bRedraw` в `SetScrollPos` 0, чтобы предотвратить перерисовываться дважды полосы прокрутки.  
  
 Разница между значениями, заданными по `nMinPos` и `nMaxPos` не должно быть больше 32 767. Диапазон по умолчанию для управления полосой прокрутки пуст (оба `nMinPos` и `nMaxPos` : 0).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]  
  
##  <a name="showscrollbar"></a>CScrollBar::ShowScrollBar  
 Показывает или скрывает полосу прокрутки.  
  
```  
void ShowScrollBar(BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bShow`  
 Указывает, видима или скрыта ли полосы прокрутки. Если этот параметр имеет **TRUE**, полосы прокрутки; в противном случае он скрыт.  
  
### <a name="remarks"></a>Примечания  
 Приложение не должно вызывать эту функцию, чтобы скрыть полосу прокрутки при обработке сообщения уведомления полосы прокрутки.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CScrollBar::Create](#create).  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Класс CButton](../../mfc/reference/cbutton-class.md)   
 [CComboBox-класс](../../mfc/reference/ccombobox-class.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)   
 [CListBox-класс](../../mfc/reference/clistbox-class.md)   
 [Класс CStatic](../../mfc/reference/cstatic-class.md)   
 [Класс CDialog](../../mfc/reference/cdialog-class.md)
