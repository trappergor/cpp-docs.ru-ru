---
title: Класс CMFCPropertyGridToolTipCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 574da3d370a403aa74ba8c438b7c175bee19f198
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211969"
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
|[CMFCPropertyGridToolTipCtrl::Create](#create)|Создает окно для элемента управления tooltip.|  
|[CMFCPropertyGridToolTipCtrl::Deactivate](#deactivate)|Отключает и скрывает элемент управления tooltip.|  
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|Возвращает координаты последней позиции элемента управления tooltip.|  
|[CMFCPropertyGridToolTipCtrl::Hide](#hide)|Скрывает элемент управления tooltip.|  
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для преобразования сообщений окна перед их отправкой к [TranslateMessage](https://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](https://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|Задает расстояние между текстом всплывающей подсказки и границы окна всплывающей подсказки.|  
|[CMFCPropertyGridToolTipCtrl::Track](#track)|Отображает элемент управления tooltip.|  
  
## <a name="remarks"></a>Примечания  
 Всплывающие подсказки отображаются при наведении указателя на имя свойства. [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) класс отображает подсказку, так как это читаемые пользователем. Как правило положение всплывающей подсказки определяется положением указателя. С помощью этого класса, подсказка отображается над имя свойства и напоминает расширение естественным свойство, так что имя свойства становится полностью видимым.  
  
 MFC автоматически создает этот элемент управления и использует его в [класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта класса `CMFCPropertyGridToolTipCtrl` , а также для отображения элемента управления tooltip.  
  
 [!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxpropertygridtooltipctrl.h  
  
##  <a name="cmfcpropertygridtooltipctrl"></a>  CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl  
 Создает объект `CMFCPropertyGridToolTipCtrl`.  
  
```  
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```  
  
##  <a name="create"></a>  CMFCPropertyGridToolTipCtrl::Create  
 Создает окно для элемента управления tooltip.  
  
```  
BOOL Create(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pWndParent*  
 Указатель на родительское окно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если окно был успешно создан; в противном случае — значение FALSE.  
  
##  <a name="deactivate"></a>  CMFCPropertyGridToolTipCtrl::Deactivate  
 Отключает и скрывает элемент управления tooltip.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод задает положение и текст последнего пустых значениях необходимо знать, таким образом, чтобы вызовы будущего [CMFCPropertyGridToolTipCtrl::Track](#track) отображения всплывающей подсказки.  
  
##  <a name="getlastrect"></a>  CMFCPropertyGridToolTipCtrl::GetLastRect  
 Возвращает координаты последней позиции элемента управления tooltip.  
  
```  
void GetLastRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [out] *rect*  
 Содержит последней позиции элемента управления tooltip.  
  
##  <a name="hide"></a>  CMFCPropertyGridToolTipCtrl::Hide  
 Скрывает элемент управления tooltip.  
  
```  
void Hide();
```  
  
##  <a name="settextmargin"></a>  CMFCPropertyGridToolTipCtrl::SetTextMargin  
 Задает расстояние между текстом всплывающей подсказки и границы окна всплывающей подсказки.  
  
```  
void SetTextMargin(int nTextMargin);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nTextMargin*  
 Задает расстояние между текст всплывающей подсказки элемента управления и границей окна всплывающей подсказки. Значение по умолчанию — 10 пикселей.  
  
##  <a name="track"></a>  CMFCPropertyGridToolTipCtrl::Track  
 Отображает элемент управления tooltip.  
  
```  
void Track(
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *rect*  
 Указывает положение и размер элемента управления tooltip.  
  
 [in] *strText*  
 Задает текст, отображаемый во всплывающей подсказке.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отображает элемент управления всплывающей подсказки в положение и размер, указанный параметром *rect*. Если позиция, размер и текст не изменились с момента последнего этот метод был вызван, этот метод не действует.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
