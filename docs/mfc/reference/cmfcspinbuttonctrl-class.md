---
title: "Класс CMFCSpinButtonCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
dev_langs: C++
helpviewer_keywords: CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd6ef1957b1f4994bafa9546581e2588e33d11a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcspinbuttonctrl-class"></a>Класс CMFCSpinButtonCtrl
`CMFCSpinButtonCtrl` Класс поддерживает наглядный диспетчер, который рисует элемент управления "Счетчик".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCSpinButtonCtrl : public CSpinButtonCtrl  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|Конструктор по умолчанию.|  
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCSpinButtonCtrl::OnDraw](#ondraw)|Перерисовывает текущий счетчик-элемент управления.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы использовать Диспетчер визуальных для отрисовки в приложении регулятор, замените все вхождения `CSpinButtonCtrl` класса `CMFCSpinButtonCtrl` класса.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как создать объект `CMFCSpinButtonCtrl` класс и использовать его `Create` метод.  
  
 [!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)  
  
 [CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxspinbuttonctrl.h  
  
##  <a name="ondraw"></a>CMFCSpinButtonCtrl::OnDraw  
 Перерисовывает текущий счетчик-элемент управления.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает `CMFCSpinButtonCtrl::OnPaint` метод для обработки [CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint) сообщение и, в свою очередь вызывает метод, это `CMFCSpinButtonCtrl::OnDraw` метод. Переопределите этот метод для настройки способа, платформа строит счетчик-элемент управления.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)
