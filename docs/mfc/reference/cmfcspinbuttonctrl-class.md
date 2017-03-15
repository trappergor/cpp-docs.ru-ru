---
title: "Класс CMFCSpinButtonCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCSpinButtonCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCSpinButtonCtrl class
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
caps.latest.revision: 25
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: c1832062461f2ed53df07a72428089179ed493ab
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcspinbuttonctrl-class"></a>Класс CMFCSpinButtonCtrl
`CMFCSpinButtonCtrl` Класс поддерживает наглядный диспетчер, который рисует элемент управления "Счетчик".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCSpinButtonCtrl : public CSpinButtonCtrl  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|Конструктор по умолчанию.|  
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCSpinButtonCtrl::OnDraw](#ondraw)|Обновляет текущий счетчик-элемент управления.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы использовать диспетчер визуального представления для рисования регулятор в приложении, замените все вхождения `CSpinButtonCtrl` класса `CMFCSpinButtonCtrl` класса.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта `CMFCSpinButtonCtrl` класс и использовать его `Create` метод.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#25;](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)  
  
 [CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxspinbuttonctrl.h  
  
##  <a name="a-nameondrawa--cmfcspinbuttonctrlondraw"></a><a name="ondraw"></a>CMFCSpinButtonCtrl::OnDraw  
 Обновляет текущий счетчик-элемент управления.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает функцию `CMFCSpinButtonCtrl::OnPaint` метод для обработки [CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint) сообщение, и что в свою очередь вызывает метод, это `CMFCSpinButtonCtrl::OnDraw` метод. Переопределите этот метод для настройки способа, платформа строит счетчик-элемент управления.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

