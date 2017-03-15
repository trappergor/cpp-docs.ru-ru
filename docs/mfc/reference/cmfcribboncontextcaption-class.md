---
title: "Класс CMFCRibbonContextCaption | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonContextCaption
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonContextCaption class
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 54f71af5ec46a8ddac4459e9ffdbc5b10f3106d4
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncontextcaption-class"></a>Класс CMFCRibbonContextCaption
Реализует цветной заголовок, который отображается в верхней части категории "лента" или категории "контекст".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonContextCaption : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCRibbonContextCaption::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCRibbonContextCaption::GetColor](#getcolor)|Возвращает цвет заголовка.|  
|[CMFCRibbonContextCaption::GetRightTabX](#getrighttabx)||  
|`CMFCRibbonContextCaption::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
  
## <a name="remarks"></a>Примечания  
 Создать экземпляр этого класса напрямую невозможно. [Класса CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md) класса этот класс используется внутренне для добавления цвета для категории ленты.  
  
 Чтобы задать цвета для категории ленты, вызовите [CMFCRibbonCategory::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor). Чтобы задать цвета для категории контекст, вызовите [CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRibbonBar.h  
  
##  <a name="a-namegetcolora--cmfcribboncontextcaptiongetcolor"></a><a name="getcolor"></a>CMFCRibbonContextCaption::GetColor  
 Возвращает цвет фона заголовка.  
  
```  
AFX_RibbonCategoryColor GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение может быть одним из следующих значений:  
  
- `AFX_CategoryColor_None`  
  
- `AFX_CategoryColor_Red`  
  
- `AFX_CategoryColor_Orange`  
  
- `AFX_CategoryColor_Yellow`  
  
- `AFX_CategoryColor_Green`  
  
- `AFX_CategoryColor_Blue`  
  
- `AFX_CategoryColor_Indigo`  
  
- `AFX_CategoryColor_Violet`  
  
### <a name="remarks"></a>Примечания  
 Цвет заголовка можно задать путем вызова [CMFCRibbonCategory::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor) или [CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory).  
  
##  <a name="a-namegetrighttabxa--cmfcribboncontextcaptiongetrighttabx"></a><a name="getrighttabx"></a>CMFCRibbonContextCaption::GetRightTabX  
 Получает положение правой границы категории вкладки ленты.  
  
```  
int GetRightTabX() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает правое значение X прямоугольника, включающего `CMFCRibbonCategory` вкладки ленты объекта, или значение -1, если вкладка усекается.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)   
 [Класс CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md)   
 [Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)

