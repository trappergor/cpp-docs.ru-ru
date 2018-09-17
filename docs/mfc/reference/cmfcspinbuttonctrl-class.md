---
title: Класс CMFCSpinButtonCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
dev_langs:
- C++
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 960a1a0338a3390fdc10cf03ddc235bcf4ecbae9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712755"
---
# <a name="cmfcspinbuttonctrl-class"></a>Класс CMFCSpinButtonCtrl
`CMFCSpinButtonCtrl` Класс поддерживает наглядный диспетчер, который рисует элемент управления "Счетчик".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCSpinButtonCtrl : public CSpinButtonCtrl  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|Конструктор по умолчанию.|  
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCSpinButtonCtrl::OnDraw](#ondraw)|Перерисовывает текущего управления "Счетчик".|  
  
## <a name="remarks"></a>Примечания  
 Чтобы использовать Диспетчер визуальных для рисования управления "Счетчик" в приложении, замените все вхождения `CSpinButtonCtrl` класса `CMFCSpinButtonCtrl` класса.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как создать объект `CMFCSpinButtonCtrl` и использовать его `Create` метод.  
  
 [!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)  
  
 [CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxspinbuttonctrl.h  
  
##  <a name="ondraw"></a>  CMFCSpinButtonCtrl::OnDraw  
 Перерисовывает текущего управления "Счетчик".  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
*основного контроллера домена*<br/>
[in] Указатель на контекст устройства.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает `CMFCSpinButtonCtrl::OnPaint` метод для обработки [CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint) сообщение, и что в свою очередь вызывает метод, это `CMFCSpinButtonCtrl::OnDraw` метод. Переопределите этот метод для настройки способа framework рисует управления "Счетчик".  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)
