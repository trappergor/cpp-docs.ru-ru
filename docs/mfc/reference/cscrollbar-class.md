---
title: "Класс CScrollBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- CScrollBar class
- SCROLLBAR window class
- scroll bars
- Windows common controls [C++], CScrollBar
- controls [MFC], scroll bar
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
caps.latest.revision: 21
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
ms.openlocfilehash: 84b59f041f1a6cf73843c303e1a6b71adffc2101
ms.lasthandoff: 02/24/2017

---
# <a name="cscrollbar-class"></a>Класс CScrollBar
Предоставляет функции элемента управления полосой прокрутки Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CScrollBar : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CScrollBar::CScrollBar](#cscrollbar)|Создает объект `CScrollBar`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CScrollBar::Create](#create)|Полоса прокрутки Windows создает и присоединяет его к `CScrollBar` объекта.|  
|[CScrollBar::EnableScrollBar](#enablescrollbar)|Включает или выключает одну или обе стрелки полосы прокрутки.|  
|[CScrollBar::GetScrollBarInfo](#getscrollbarinfo)|Извлекает сведения о полосы с помощью прокрутки `SCROLLBARINFO` структуры.|  
|[CScrollBar::GetScrollInfo](#getscrollinfo)|Извлекает сведения о полосе прокрутки.|  
|[CScrollBar::GetScrollLimit](#getscrolllimit)|Извлекает ограничение полосы прокрутки|  
|[CScrollBar::GetScrollPos](#getscrollpos)|Извлекает текущее положение ползунка.|  
|[CScrollBar::GetScrollRange](#getscrollrange)|Извлекает текущей позиции минимальное и максимальное полосы прокрутки полосы прокрутки заданной.|  
|[CScrollBar::SetScrollInfo](#setscrollinfo)|Задает сведения о полосе прокрутки.|  
|[CScrollBar::SetScrollPos](#setscrollpos)|Задает текущее положение ползунка полосы прокрутки.|  
|[CScrollBar::SetScrollRange](#setscrollrange)|Задает для указанной полосы прокрутки положения минимума и максимума.|  
|[CScrollBar::ShowScrollBar](#showscrollbar)|Показывает или скрывает полосы прокрутки.|  
  
## <a name="remarks"></a>Примечания  
 Создание элемента управления полосы прокрутки в два этапа. Во-первых, вызовите конструктор `CScrollBar` для создания `CScrollBar` , а затем вызвать [создать](#create) функции-члена для создания элемента управления полосой прокрутки Windows и присоединить его к `CScrollBar` объекта.  
  
 При создании `CScrollBar` объекта в диалоговое окно (с помощью ресурса диалогового окна) `CScrollBar` автоматически освобождается, когда пользователь закрывает окно.  
  
 При создании `CScrollBar` объекта в окне, необходимо уничтожить его.  
  
 При создании `CScrollBar` объекта в стеке удаляется автоматически. При создании `CScrollBar` объектов в куче с помощью **новый** функции, необходимо вызвать **удаление** для объекта, чтобы уничтожить его, когда пользователь завершает полосу прокрутки Windows.  
  
 Если выделять память в `CScrollBar` объекта, переопределить `CScrollBar` деструктор для удаления распределения.  
  
 Дополнительные сведения об использовании `CScrollBar`, в разделе [управления](../../mfc/controls-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CScrollBar`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="create"></a>CScrollBar::Create  
 Полоса прокрутки Windows создает и присоединяет его к `CScrollBar` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Указывает прокрутки стиль элемента диаграммы. Примените любое сочетание [стили полосы прокрутки](../../mfc/reference/scroll-bar-styles.md) полосу прокрутки.  
  
 `rect`  
 Указывает размер полосы прокрутки и положение. Может быть либо `RECT` структуры или `CRect` объекта.  
  
 `pParentWnd`  
 Указывает прокрутки линейки родительского окна, обычно `CDialog` объекта. Оно не должно быть **NULL**.  
  
 `nID`  
 Идентификатор элемента управления полосы прокрутки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CScrollBar` объекта в два этапа. Во-первых, вызовите конструктор, который создает `CScrollBar` объекта, затем вызовите **создать**, который создает и инициализирует полосу прокрутки связанные Windows и присоединяет его к `CScrollBar` объекта.  
  
 Примените следующий [стили окна](../../mfc/reference/window-styles.md) полосу прокрутки:  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
- **WS_GROUP** для группирования элементов управления  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CScrollBar&#1;](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]  
  
##  <a name="cscrollbar"></a>CScrollBar::CScrollBar  
 Создает объект `CScrollBar`.  
  
```  
CScrollBar();
```  
  
### <a name="remarks"></a>Примечания  
 После создания объекта, вызовите метод **создать** функции-члена для создания и инициализации полосу прокрутки Windows.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CScrollBar&#2;](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]  
  
##  <a name="enablescrollbar"></a>CScrollBar::EnableScrollBar  
 Включает или выключает одну или обе стрелки полосы прокрутки.  
  
```  
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```  
  
### <a name="parameters"></a>Параметры  
 `nArrowFlags`  
 Указывает стрелками включена ли и какие стрелки включены или отключены. Этот параметр может принимать одно из следующих значений:  
  
- **ESB_ENABLE_BOTH** позволяет обе стрелки полосы прокрутки.  
  
- **ESB_DISABLE_LTUP** отключает стрелку влево для горизонтальной полосы прокрутки или со стрелкой вверх для вертикальной полосы прокрутки.  
  
- **ESB_DISABLE_RTDN** отключает стрелку вправо для горизонтальной полосы прокрутки или стрелку вниз для вертикальной полосы прокрутки.  
  
- **ESB_DISABLE_BOTH** отключает обе стрелки полосы прокрутки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если включены или отключены в соответствии; стрелки в противном случае — 0, означающее, что стрелки уже запрошенное состояние или произошла ошибка.  
  
### <a name="example"></a>Пример  
  В примере показано [CScrollBar::SetScrollRange](#setscrollrange).  
  
##  <a name="getscrollbarinfo"></a>CScrollBar::GetScrollBarInfo  
 Возвращает сведения, **SCROLLBARINFO** структура поддерживает о полосы прокрутки.  
  
```  
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *pScrollInfo*  
 Указатель на [SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787535) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [SBM_SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787545) сообщений, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getscrollinfo"></a>CScrollBar::GetScrollInfo  
 Извлекает данные о полосе прокрутки, содержащиеся в структуре `SCROLLINFO`.  
  
```  
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,  
    UINT nMask = SIF_ALL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpScrollInfo`  
 Указатель на [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) структуры. В разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения о структуре.  
  
 `nMask`  
 Указывает параметры панель прокрутки для извлечения. Типичное использование SIF_ALL, задает сочетание SIF_PAGE, SIF_POS, SIF_TRACKPOS и SIF_RANGE. В разделе `SCROLLINFO` Дополнительные сведения о значениях nMask.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если сообщение получено, все значения, возвращаемое значение **TRUE**. В противном случае, это **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 `GetScrollInfo`позволяет приложениям использовать позиции прокрутки 32-разрядной.  
  
 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) структура содержит сведения о полосы прокрутки, включая минимальные и максимальные прокрутка позиций, размер страницы и положение полосы прокрутки (бегунком). В разделе `SCROLLINFO` раздел структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения об изменении структуры значения по умолчанию.  
  
 Сообщения MFC Windows обработчики, которые указывают на расположение полосы прокрутки, [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) и [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll), предоставляют только 16 битов позиции данных. `GetScrollInfo`и `SetScrollInfo` обеспечивают 32 бита полосы данных позиции прокрутки. Таким образом, приложение может вызвать `GetScrollInfo` при обработке либо `CWnd::OnHScroll` или `CWnd::OnVScroll` для получения данных позиции прокрутки 32-разрядной панели.  
  
### <a name="example"></a>Пример  
  В примере показано [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrolllimit"></a>CScrollBar::GetScrollLimit  
 Получает максимальное прокрутка положение полосы прокрутки.  
  
```  
int GetScrollLimit();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указывает положение полосы прокрутки в случае успешного выполнения; в противном случае — 0.  
  
### <a name="example"></a>Пример  
  В примере показано [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrollpos"></a>CScrollBar::GetScrollPos  
 Извлекает текущее положение ползунка.  
  
```  
int GetScrollPos() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Задает текущее положение ползунка полосы прокрутки, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Текущая позиция находится относительное значение, от которого зависит от текущего диапазона прокрутки. Например если полосы прокрутки не в середине полосы прокрутки диапазон — от 100 до 200, текущая позиция — 150.  
  
### <a name="example"></a>Пример  
  В примере показано [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrollrange"></a>CScrollBar::GetScrollRange  
 Копирует в расположениях, указанных в текущей позиции минимальное и максимальное полосы прокрутки полосы прокрутки данного `lpMinPos` и `lpMaxPos`.  
  
```  
void GetScrollRange(
    LPINT lpMinPos,  
    LPINT lpMaxPos) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpMinPos`  
 Указывает, получающего минимальной позиции целочисленной переменной.  
  
 `lpMaxPos`  
 Указывает, получающего положение целочисленной переменной.  
  
### <a name="remarks"></a>Примечания  
 Диапазон по умолчанию для элемента управления полосы прокрутки пуст (оба значения равны 0).  
  
### <a name="example"></a>Пример  
  В примере показано [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="setscrollinfo"></a>CScrollBar::SetScrollInfo  
 Задает сведения, `SCROLLINFO` структура поддерживает о полосы прокрутки.  
  
```  
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `lpScrollInfo`  
 Указатель на [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) структуры.  
  
 `bRedraw`  
 Указывает, следует ли заново полосы прокрутки, с учетом новых данных. Если `bRedraw` — **TRUE**, перерисовке полосы прокрутки. Если это **FALSE**, не перерисовывается. По умолчанию перерисовке полосы прокрутки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении возвращается **TRUE**. В противном случае, это **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Необходимо указать значения, необходимые для `SCROLLINFO` структуру параметров, включая значения флага.  
  
 `SCROLLINFO` Структура содержит сведения о полосы прокрутки, включая минимальные и максимальные прокрутка позиций, размер страницы и положение полосы прокрутки (бегунком). В разделе [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) раздел структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения об изменении структуры значения по умолчанию.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CScrollBar&#3;](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]  
  
##  <a name="setscrollpos"></a>CScrollBar::SetScrollPos  
 Задает текущее положение ползунка полосы прокрутки, указанному для `nPos` и, если указано, перерисовывает полосу прокрутки для отображения нового положения.  
  
```  
int SetScrollPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Указывает новое положение для полосы прокрутки. Он должен находиться в диапазоне прокрутки.  
  
 `bRedraw`  
 Указывает, следует ли заново полосы прокрутки, с учетом новой позиции. Если `bRedraw` — **TRUE**, перерисовке полосы прокрутки. Если это **FALSE**, не перерисовывается. По умолчанию перерисовке полосы прокрутки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указывает, предыдущей позиции ползунка полосы прокрутки, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Задайте `bRedraw` для **FALSE** каждый раз, когда полоса прокрутки перерисовывается при последующих вызовах другой функции, чтобы избежать необходимости полосы прокрутки, перерисовке дважды в течение короткого промежутка времени.  
  
### <a name="example"></a>Пример  
  В примере показано [CScrollBar::SetScrollRange](#setscrollrange).  
  
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
 Задает минимальный позиции прокрутки.  
  
 `nMaxPos`  
 Определяет максимальное позиции прокрутки.  
  
 `bRedraw`  
 Указывает, следует ли полосы прокрутки перерисовку в соответствии с изменениями. Если `bRedraw` — **TRUE**, перерисовке полосы прокрутки; Если **FALSE**, не перерисовывается. Перерисовке по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Задайте `nMinPos` и `nMaxPos` 0, чтобы скрыть полосы прокрутки standard.  
  
 Не вызывайте эту функцию, чтобы скрыть полосу прокрутки при обработке сообщения уведомления полосы прокрутки.  
  
 Если вызов `SetScrollRange` сразу же после вызова функции для `SetScrollPos` функция-член, установите `bRedraw` в `SetScrollPos` 0, чтобы предотвратить перерисовываться дважды полосы прокрутки.  
  
 Разница между значениями, указанными `nMinPos` и `nMaxPos` не должно быть больше 32 767. Диапазон по умолчанию для элемента управления полосы прокрутки пуст (оба `nMinPos` и `nMaxPos` , 0).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CScrollBar&#4;](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]  
  
##  <a name="showscrollbar"></a>CScrollBar::ShowScrollBar  
 Показывает или скрывает полосы прокрутки.  
  
```  
void ShowScrollBar(BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bShow`  
 Указывает, показаны или скрыты полосы прокрутки. Если этот параметр равен **TRUE**, полоса прокрутки отображается; в противном случае он скрыт.  
  
### <a name="remarks"></a>Примечания  
 Приложение не должно вызывать эту функцию, чтобы скрыть полосу прокрутки при обработке сообщения уведомления полосы прокрутки.  
  
### <a name="example"></a>Пример  
  В примере показано [CScrollBar::Create](#create).  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Класс CButton](../../mfc/reference/cbutton-class.md)   
 [CComboBox-класс](../../mfc/reference/ccombobox-class.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)   
 [CListBox-класс](../../mfc/reference/clistbox-class.md)   
 [Класс CStatic](../../mfc/reference/cstatic-class.md)   
 [CDialog-класс](../../mfc/reference/cdialog-class.md)

