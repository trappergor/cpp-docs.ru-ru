---
title: "Макросы класс окна | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
caps.latest.revision: 16
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
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: f32926b6efd4ffb9c0541c0574a479c13dac01df
ms.lasthandoff: 02/24/2017

---
# <a name="window-class-macros"></a>Макросы класса окна
Эти макросы определить служебных программ класса окна.  
  
|||  
|-|-|  
|[DECLARE_WND_CLASS](#declare_wnd_class)|Позволяет указать имя класса окна.| 
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017 г.) Позволяет указать имя нового класса окна и включающего класса, Оконная процедура будет использовать новый класс.| 
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|Позволяет указать имя существующий класс окон, на котором будет основан новый класс окна.|  
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|Позволяет указать параметры класса.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
   
##  <a name="a-namedeclarewndclassa--declarewndclass"></a><a name="declare_wnd_class"></a>DECLARE_WND_CLASS  
 Позволяет указать имя класса окна. Поместите этот макрос в элемент управления ATL ActiveX класса элемента управления.  
  
```
DECLARE_WND_CLASS( WndClassName )
```  
  
### <a name="parameters"></a>Параметры  
 `WndClassName`  
 [in] Имя нового класса окна. Если **NULL**, ATL создаст имя класса окна.  
  
### <a name="remarks"></a>Примечания  
 При использовании параметра /permissive-compiler DECLARE_WND_CLASS приведет к ошибке компилятора; Вместо этого используйте DECLARE_WND_CLASS2.
 
 DECLARE_WND_CLASS позволяет указать имя, сведения о которых будут управляться с помощью нового класса окна [CWndClassInfo](cwndclassinfo-class.md). `DECLARE_WND_CLASS`Определяет класс новые окна путем реализации следующих статическую функцию:  
  
 [!code-cpp[NVC_ATL_Windowing&#127;](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 `DECLARE_WND_CLASS`Задает для нового окна следующие стили:  
  
-   CS_HREDRAW  
  
-   CS_VREDRAW  
  
-   CS_DBLCLKS  
  
 `DECLARE_WND_CLASS`также задает цвет фона окна по умолчанию. Используйте [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) макрос для предоставления собственных стилей и цвет фона.  
  
 [CWindowImpl](cwindowimpl-class.md) использует `DECLARE_WND_CLASS` макрос для создания окна на основании нового класса окна. Чтобы переопределить это поведение, используйте [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) макрос, или предоставить собственную реализацию [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) функции.  

  
 Дополнительные сведения об использовании windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).  

##  <a name="a-namedeclarewndclass2a--declarewndclass2"></a><a name="declare_wnd_class2"></a>DECLARE_WND_CLASS2  
 (Visual Studio 2017 г.) Аналогичен DECLARE_WND_CLASS, но с дополнительным параметром, чтобы избежать ошибок зависимое имя при компиляции с помощью /permissive-option.
  
```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```  
  
### <a name="parameters"></a>Параметры  
 `WndClassName`  
 [in] Имя нового класса окна. Если **NULL**, ATL создаст имя класса окна. 

 `EnclosingClass`  
 [in] Имя класса окна, содержащего новый класс окна. Не может быть **NULL**.  
  
### <a name="remarks"></a>Примечания 
При использовании /permissive-option DECLARE_WND_CLASS приведет к ошибке компиляции, так как он содержит зависимое имя. DECLARE_WND_CLASS2 необходимо явно указывать имя класса, что этот макрос используется и не вызывает ошибку в разделе /permissive-flag.
В противном случае этот макрос идентична [DECLARE_WND_CLASS](#declare_wnd_class).
   
##  <a name="a-namedeclarewndsuperclassa--declarewndsuperclass"></a><a name="declare_wnd_superclass"></a>DECLARE_WND_SUPERCLASS  
 Позволяет указать параметры класса. Поместите этот макрос в элемент управления ATL ActiveX класса элемента управления.  
  
```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```  
  
### <a name="parameters"></a>Параметры  
 `WndClassName`  
 [in] Имя окна класса суперкласса, будет `OrigWndClassName`. Если **NULL**, ATL создаст имя класса окна.  
  
 `OrigWndClassName`  
 [in] Имя существующего класса окна.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос позволяет указать имя класса окна, который будет суперкласса существующий класс окон. [CWndClassInfo](cwndclassinfo-class.md) управляет сведениями о суперкласса.  
  
 `DECLARE_WND_SUPERCLASS`реализует следующие статическую функцию:  
  
 [!code-cpp[NVC_ATL_Windowing&#127;](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 По умолчанию [CWindowImpl](cwindowimpl-class.md) использует [DECLARE_WND_CLASS](#declare_wnd_class) макрос для создания окна на основании нового класса окна. Указав `DECLARE_WND_SUPERCLASS` макрос в `CWindowImpl`-производного класса, класс окна будет основываться на существующий класс, но будет использовать в процедуре окна. Этот прием называется создание суперклассов.  
  
 Помимо использования `DECLARE_WND_CLASS` и `DECLARE_WND_SUPERCLASS` макросы, можно переопределить [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) функции с собственной реализации.  

  
 Дополнительные сведения об использовании windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).  
  
##  <a name="a-namedeclarewndclassexa--declarewndclassex"></a><a name="declare_wnd_class_ex"></a>DECLARE_WND_CLASS_EX  
 Позволяет указать имя существующий класс окон, на котором будет основан новый класс окна. Поместите этот макрос в элемент управления ATL ActiveX класса элемента управления.  
  
```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```  
  
### <a name="parameters"></a>Параметры  
 `WndClassName`  
 [in] Имя нового класса окна. Если **NULL**, ATL создаст имя класса окна.  
  
 `style`  
 [in] Стиль окна.  
  
 *Фоновая*  
 [in] Цвет фона окна.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос позволяет указать параметры класса новый класс окна, сведения о которых будут управляться [CWndClassInfo](cwndclassinfo-class.md). `DECLARE_WND_CLASS_EX`Определяет класс новые окна путем реализации следующих статическую функцию:  
  
 [!code-cpp[NVC_ATL_Windowing&#127;](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 Если вы хотите использовать стили по умолчанию и цвет фона, используйте [DECLARE_WND_CLASS](#declare_wnd_class) макрос. Дополнительные сведения об использовании windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).  
  
## <a name="see-also"></a>См. также  
 [Макросы](atl-macros.md)










