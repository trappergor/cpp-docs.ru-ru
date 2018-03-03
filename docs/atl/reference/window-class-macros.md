---
title: "Макросы класс окна | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlwin/ATL::DECLARE_WND_CLASS
- atlwin/ATL::DECLARE_WND_SUPERCLASS
- atlwin/ATL::DECLARE_WND_CLASS_EX
dev_langs:
- C++
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bba4b6743477ae3c3d345a20f1c2e672e73261e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="window-class-macros"></a>Макросы класса окна
Эти макросы определяют программы класс окна.  
  
|||  
|-|-|  
|[DECLARE_WND_CLASS](#declare_wnd_class)|Позволяет указать имя класса окна.| 
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017 г.) Позволяет указать имя нового класса окна и включающего класса которого новый класс будет использовать процедуру окна.| 
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|Позволяет указать имя существующего класса окна, на котором будет основан новый класс окна.|  
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|Позволяет указать параметры типа класса.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
   
##  <a name="declare_wnd_class"></a>DECLARE_WND_CLASS  
 Позволяет указать имя класса окна. Поместите этот макрос в элемент управления ActiveX библиотеки ATL класс элемента управления.  
  
```
DECLARE_WND_CLASS( WndClassName )
```  
  
### <a name="parameters"></a>Параметры  
 `WndClassName`  
 [in] Имя нового класса окна. Если **NULL**, ATL создаст имя класса окна.  
  
### <a name="remarks"></a>Примечания  
 При использовании параметра /permissive-compiler DECLARE_WND_CLASS приведет к ошибке компилятора; Вместо этого используйте DECLARE_WND_CLASS2.
 
 DECLARE_WND_CLASS позволяет указать имя нового класса окна, сведения о которых будут управляться [CWndClassInfo](cwndclassinfo-class.md). `DECLARE_WND_CLASS`Определяет новый класс окна путем реализации следующих статическую функцию:  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 `DECLARE_WND_CLASS`Задает для нового окна следующие стили:  
  
-   CS_HREDRAW  
  
-   CS_VREDRAW  
  
-   CS_DBLCLKS  
  
 `DECLARE_WND_CLASS`также задает цвет фона окна по умолчанию. Используйте [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) макрос для предоставления собственных стилей и цвет фона.  
  
 [CWindowImpl](cwindowimpl-class.md) использует `DECLARE_WND_CLASS` макрос для создания окна на основании нового класса окна. Чтобы переопределить это поведение, используйте [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) макрос, или предоставить собственную реализацию [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) функции.  

  
 Дополнительные сведения об использовании windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).  

##  <a name="declare_wnd_class2"></a>DECLARE_WND_CLASS2  
 (Visual Studio 2017 г.) Аналогичен DECLARE_WND_CLASS, но с дополнительным параметром, чтобы избежать ошибки зависимое имя при компиляции с помощью /permissive-option.
  
```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```  
  
### <a name="parameters"></a>Параметры  
 `WndClassName`  
 [in] Имя нового класса окна. Если **NULL**, ATL создаст имя класса окна. 

 `EnclosingClass`  
 [in] Имя класса окна, содержащего новый класс окна. Не может быть **NULL**.  
  
### <a name="remarks"></a>Примечания 
При использовании /permissive-option DECLARE_WND_CLASS приведет к ошибке компиляции, так как он содержит зависимое имя. DECLARE_WND_CLASS2 требуется явно указывать имя класса, этот макрос используется в и не вызовет ошибку в /permissive-flag.
В противном случае этот макрос идентична [DECLARE_WND_CLASS](#declare_wnd_class).
   
##  <a name="declare_wnd_superclass"></a>DECLARE_WND_SUPERCLASS  
 Позволяет указать параметры типа класса. Поместите этот макрос в элемент управления ActiveX библиотеки ATL класс элемента управления.  
  
```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```  
  
### <a name="parameters"></a>Параметры  
 `WndClassName`  
 [in] Имя окна класса, будет суперкласса `OrigWndClassName`. Если **NULL**, ATL создаст имя класса окна.  
  
 `OrigWndClassName`  
 [in] Имя существующего класса окна.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос позволяет указать имя класса окна, который будет суперкласса существующего класса окна. [CWndClassInfo](cwndclassinfo-class.md) управляет данными суперкласса.  
  
 `DECLARE_WND_SUPERCLASS`реализует следующие статическую функцию:  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 По умолчанию [CWindowImpl](cwindowimpl-class.md) использует [DECLARE_WND_CLASS](#declare_wnd_class) макрос для создания окна на основании нового класса окна. Путем указания `DECLARE_WND_SUPERCLASS` макрос в `CWindowImpl`-класс, производный класс окна будет основываться на существующий класс, но будет использовать процедуре окна. Этот прием называется создание суперклассов.  
  
 Помимо использования `DECLARE_WND_CLASS` и `DECLARE_WND_SUPERCLASS` макросов, можно переопределить [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) функцию с свою собственную реализацию.  

  
 Дополнительные сведения об использовании windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).  
  
##  <a name="declare_wnd_class_ex"></a>DECLARE_WND_CLASS_EX  
 Позволяет указать имя существующего класса окна, на котором будет основан новый класс окна. Поместите этот макрос в элемент управления ActiveX библиотеки ATL класс элемента управления.  
  
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
 Этот макрос можно задать параметры нового класса окна, сведения о которых будут управляться с помощью класса [CWndClassInfo](cwndclassinfo-class.md). `DECLARE_WND_CLASS_EX`Определяет новый класс окна путем реализации следующих статическую функцию:  
  
 [!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 Если вы хотите использовать стили по умолчанию и цвет фона, используйте [DECLARE_WND_CLASS](#declare_wnd_class) макрос. Дополнительные сведения об использовании windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).  
  
## <a name="see-also"></a>См. также  
 [Макросы](atl-macros.md)









