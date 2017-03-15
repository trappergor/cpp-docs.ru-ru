---
title: "Класс CMFCDisableMenuAnimation | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDisableMenuAnimation
dev_langs:
- C++
helpviewer_keywords:
- CMFCDisableMenuAnimation class
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
caps.latest.revision: 22
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
ms.openlocfilehash: ea0be944ca70d6f8317fd4bc60fdd50ecc714438
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdisablemenuanimation-class"></a>Класс CMFCDisableMenuAnimation
Отключает анимации во всплывающем меню.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCDisableMenuAnimation  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Создает объект `CMFCDisableMenuAnimation`.|  
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCDisableMenuAnimation::Restore](#restore)|Восстановление предыдущей анимации, платформа используется для отображения всплывающего меню.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCDisableMenuAnimation::m_animType`|Сохраняет предыдущий тип анимации во всплывающем меню.|  
  
### <a name="remarks"></a>Примечания  
 Используйте этот вспомогательный класс для временного отключения анимации во всплывающем меню (например, при обработке команды мыши или клавиатуры).  
  
 Объект `CMFCDisableMenuAnimation` объект отключает анимации во всплывающем меню во время существования. Конструктор сохраняет текущий тип анимации во всплывающем меню в `m_animType` и устанавливает тип текущей анимации `CMFCPopupMenu::NO_ANIMATION`. Деструктор восстанавливает предыдущий тип анимации.  
  
 Можно создать `CMFCDisableMenuAnimation` объект в стеке для отключения анимации во всплывающем меню в одной функции. Если вы хотите отключить всплывающее меню анимации между функциями, создать `CMFCDisableMenuAnimation` объекта в куче, а затем удалите его, если вы хотите восстановить анимации во всплывающем меню.  
  
## <a name="example"></a>Пример  
 Следующий пример показывает использование стека для временного отключения анимация меню.  
  
 [!code-cpp[NVC_MFC_Misc&#1;](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxpopupmenu.h  
  
##  <a name="a-namerestorea--cmfcdisablemenuanimationrestore"></a><a name="restore"></a>CMFCDisableMenuAnimation::Restore  
 Восстановление предыдущей анимации, платформа используется для отображения всплывающего меню.  
  
```  
void Restore ();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `CMFCDisableMenuAnimation` деструктор для восстановления предыдущей анимации, платформа используется для отображения всплывающего меню.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

