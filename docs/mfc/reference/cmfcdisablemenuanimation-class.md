---
title: Класс CMFCDisableMenuAnimation | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
dev_langs:
- C++
helpviewer_keywords:
- CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a7a2449fe65a0b17bf770ea2bfb8f3fe750cba0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366962"
---
# <a name="cmfcdisablemenuanimation-class"></a>Класс CMFCDisableMenuAnimation
Отключает анимацию всплывающего меню.  
  
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
|[CMFCDisableMenuAnimation::Restore](#restore)|Восстановление предыдущей анимации, которая используется платформа для отображения всплывающего меню.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCDisableMenuAnimation::m_animType`|Сохраняет предыдущий тип анимации всплывающего меню.|  
  
### <a name="remarks"></a>Примечания  
 Используйте этот вспомогательный класс для временного отключения анимации всплывающего меню (например, при обработке команды мыши или клавиатуры).  
  
 Объект `CMFCDisableMenuAnimation` объект отключает анимацию всплывающего меню во время существования. Конструктор сохраняет текущий тип анимации всплывающего меню в `m_animType` и устанавливает тип текущей анимацией `CMFCPopupMenu::NO_ANIMATION`. Деструктор восстанавливает предыдущий тип анимации.  
  
 Можно создать `CMFCDisableMenuAnimation` объект в стеке для отключения анимации всплывающего меню в одной функции. Если вы хотите отключить анимация всплывающее меню между функциями, создайте `CMFCDisableMenuAnimation` объекта в куче, а затем удалите его, если вы хотите восстановить анимации всплывающего меню.  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование стека для временного отключения анимация меню.  
  
 [!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxpopupmenu.h  
  
##  <a name="restore"></a>  CMFCDisableMenuAnimation::Restore  
 Восстановление предыдущей анимации, которая используется платформа для отображения всплывающего меню.  
  
```  
void Restore ();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `CMFCDisableMenuAnimation` деструктор для восстановления предыдущей анимации, которая используется платформа для отображения всплывающего меню.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)
