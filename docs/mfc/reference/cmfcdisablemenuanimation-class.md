---
title: "Класс CMFCDisableMenuAnimation | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 458a35e708db41ee393da70aedd653aca44cf802
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcdisablemenuanimation-class"></a>Класс CMFCDisableMenuAnimation
Отключает анимацию всплывающего меню.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCDisableMenuAnimation  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Создает объект `CMFCDisableMenuAnimation`.|  
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCDisableMenuAnimation::Restore](#restore)|Восстановление предыдущей анимации, которая используется платформа для отображения всплывающего меню.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|name|Описание:|  
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
  
##  <a name="restore"></a>CMFCDisableMenuAnimation::Restore  
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
