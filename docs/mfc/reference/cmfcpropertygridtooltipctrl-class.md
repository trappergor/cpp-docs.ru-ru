---
title: "Класс CMFCPropertyGridToolTipCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Create
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Deactivate
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::GetLastRect
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Hide
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::SetTextMargin
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Track
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridToolTipCtrl class
- CMFCPropertyGridToolTipCtrl class, destructor
- PreTranslateMessage method
- ~CMFCPropertyGridToolTipCtrl destructor
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
caps.latest.revision: 24
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
ms.openlocfilehash: e5290706799dcd253205ac74dad72cd7783d19dd
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridtooltipctrl-class"></a>Класс CMFCPropertyGridToolTipCtrl
Реализует подсказку, управления, [CMFCPropertyGridCtrl класс](../../mfc/reference/cmfcpropertygridctrl-class.md) используется для отображения подсказки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPropertyGridToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|Создает объект `CMFCPropertyGridToolTipCtrl`.|  
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCPropertyGridToolTipCtrl::Create](#create)|Создает окно для элемента управления всплывающей подсказки.|  
|[CMFCPropertyGridToolTipCtrl::Deactivate](#deactivate)|Отключает и скрывает элемент управления всплывающей подсказки.|  
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|Возвращает координаты последней позиции элемента управления всплывающей подсказки.|  
|[CMFCPropertyGridToolTipCtrl::Hide](#hide)|Скрывает элемент управления всплывающей подсказки.|  
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для перевода оконных сообщений перед их отправкой [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|Задает расстояние между текст подсказки и границы окна всплывающей подсказки.|  
|[CMFCPropertyGridToolTipCtrl::Track](#track)|Отображает элемент управления всплывающей подсказки.|  
  
## <a name="remarks"></a>Примечания  
 Всплывающие подсказки отображается при наведении указателя на имя свойства. [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) класса отображается всплывающая подсказка, чтобы оно было легко читать пользователем. Как правило положения подсказки определяется положением указателя. С помощью этого класса, подсказка отображается над имя свойства и напоминает расширение естественным свойство, чтобы полностью отображается имя свойства.  
  
 MFC автоматически создается этот элемент управления, который используется в [CMFCPropertyGridCtrl класса](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создания объекта `CMFCPropertyGridToolTipCtrl` и способ отображения элемента управления всплывающей подсказки.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#23;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxpropertygridtooltipctrl.h  
  
##  <a name="cmfcpropertygridtooltipctrl"></a>CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl  
 Создает объект `CMFCPropertyGridToolTipCtrl`.  
  
```  
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```  
  
##  <a name="create"></a>CMFCPropertyGridToolTipCtrl::Create  
 Создает окно для элемента управления всплывающей подсказки.  
  
```  
BOOL Create(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Указатель на родительское окно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если окно был успешно создан; в противном случае — значение FALSE.  
  
##  <a name="deactivate"></a>CMFCPropertyGridToolTipCtrl::Deactivate  
 Отключает и скрывает элемент управления всплывающей подсказки.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод задает текст и положение последнего пустые значения, чтобы вызовы будущего [CMFCPropertyGridToolTipCtrl::Track](#track) отображения всплывающей подсказки.  
  
##  <a name="getlastrect"></a>CMFCPropertyGridToolTipCtrl::GetLastRect  
 Возвращает координаты последней позиции элемента управления всплывающей подсказки.  
  
```  
void GetLastRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rect`  
 Содержит последней позиции элемента управления всплывающей подсказки.  
  
##  <a name="hide"></a>CMFCPropertyGridToolTipCtrl::Hide  
 Скрывает элемент управления всплывающей подсказки.  
  
```  
void Hide();
```  
  
##  <a name="settextmargin"></a>CMFCPropertyGridToolTipCtrl::SetTextMargin  
 Задает расстояние между текст подсказки и границы окна всплывающей подсказки.  
  
```  
void SetTextMargin(int nTextMargin);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nTextMargin`  
 Задает расстояние между текст всплывающей подсказки элемента управления и границей окна всплывающей подсказки. Значение по умолчанию — 10 точек.  
  
##  <a name="track"></a>CMFCPropertyGridToolTipCtrl::Track  
 Отображает элемент управления всплывающей подсказки.  
  
```  
void Track(
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
 Указывает положение и размер элемента управления всплывающей подсказки.  
  
 [in] `strText`  
 Задает текст, отображаемый во всплывающей подсказке.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отображает элемент управления всплывающей подсказки в положение и размер, указанный параметром `rect`. Если позиция, размер и текст не изменились со времени последнего вызова этого метода, этот метод не оказывает влияния.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

