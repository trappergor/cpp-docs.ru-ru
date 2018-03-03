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
- CMFCPropertyGridToolTipCtrl [MFC], CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl [MFC], Create
- CMFCPropertyGridToolTipCtrl [MFC], Deactivate
- CMFCPropertyGridToolTipCtrl [MFC], GetLastRect
- CMFCPropertyGridToolTipCtrl [MFC], Hide
- CMFCPropertyGridToolTipCtrl [MFC], SetTextMargin
- CMFCPropertyGridToolTipCtrl [MFC], Track
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a0b4a43da8943bc196a799ca4419dea7f34ed76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>Класс CMFCPropertyGridToolTipCtrl
Реализует подсказку, управления, [класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) используется для отображения подсказки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPropertyGridToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|Создает объект `CMFCPropertyGridToolTipCtrl`.|  
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCPropertyGridToolTipCtrl::Create](#create)|Создает окно для элемента управления всплывающей подсказки.|  
|[CMFCPropertyGridToolTipCtrl::Deactivate](#deactivate)|Отключает и скрывает элемент управления tooltip.|  
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|Возвращает координаты последней позиции элемента управления tooltip.|  
|[CMFCPropertyGridToolTipCtrl::Hide](#hide)|Скрывает элемент управления tooltip.|  
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для преобразования сообщений окна перед их передачей функциям Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) . (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|Задает интервал между текст всплывающей подсказки и границы окна всплывающей подсказки.|  
|[CMFCPropertyGridToolTipCtrl::Track](#track)|Отображает элемент управления tooltip.|  
  
## <a name="remarks"></a>Примечания  
 Всплывающие подсказки отображается при наведении указателя мыши на имя свойства. [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) класса отображаются всплывающие подсказки, чтобы оно было легко читать пользователем. Как правило положения подсказки определяется положения указателя. С помощью этого класса, всплывающая подсказка отображается над имя свойства и напоминает расширение естественным свойство, чтобы полностью отображается имя свойства.  
  
 MFC автоматически создается элемент управления, который используется в [класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта `CMFCPropertyGridToolTipCtrl` и способ отображения элемента управления всплывающей подсказки.  
  
 [!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]  
  
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
 Отключает и скрывает элемент управления tooltip.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод устанавливает последней позиции и текст пустые значения, чтобы будущие вызовы [CMFCPropertyGridToolTipCtrl::Track](#track) отображения всплывающей подсказки.  
  
##  <a name="getlastrect"></a>CMFCPropertyGridToolTipCtrl::GetLastRect  
 Возвращает координаты последней позиции элемента управления tooltip.  
  
```  
void GetLastRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rect`  
 Содержит последней позиции элемента управления tooltip.  
  
##  <a name="hide"></a>CMFCPropertyGridToolTipCtrl::Hide  
 Скрывает элемент управления tooltip.  
  
```  
void Hide();
```  
  
##  <a name="settextmargin"></a>CMFCPropertyGridToolTipCtrl::SetTextMargin  
 Задает интервал между текст всплывающей подсказки и границы окна всплывающей подсказки.  
  
```  
void SetTextMargin(int nTextMargin);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nTextMargin`  
 Задает расстояние между текст всплывающей подсказки элемента управления и границей окна всплывающей подсказки. Значение по умолчанию — 10 точек.  
  
##  <a name="track"></a>CMFCPropertyGridToolTipCtrl::Track  
 Отображает элемент управления tooltip.  
  
```  
void Track(
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
 Задает положение и размер элемента управления tooltip.  
  
 [in] `strText`  
 Задает текст, отображаемый во всплывающей подсказке.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отображает элемент управления tooltip в положение и размер, указанный параметром `rect`. Если расположение, размер и текст не изменились со времени последнего вызова этого метода, этот метод не оказывает влияния.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
