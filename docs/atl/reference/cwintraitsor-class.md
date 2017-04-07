---
title: "Класс CWinTraitsOR | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
dev_langs:
- C++
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
caps.latest.revision: 20
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
ms.openlocfilehash: cd077c7f79c3099d0e825a48233e7a8b269c0d04
ms.lasthandoff: 02/24/2017

---
# <a name="cwintraitsor-class"></a>Класс CWinTraitsOR
Этот класс предоставляет метод для стандартизации стили, используемые при создании объекта окна.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0, 
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```  
  
#### <a name="parameters"></a>Параметры  
 `t_dwStyle`  
 Стили окна по умолчанию.  
  
 `t_dwExStyle`  
 По умолчанию расширенные стили окна.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|Извлекает расширенные стили для `CWinTraitsOR` объекта.|  
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|Получает стандартный стили `CWinTraitsOR` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Это [характеристик окна](../../atl/understanding-window-traits.md) класс предоставляет простой способ для стандартизации стили, используемые для создания объекта окна ATL. Использование в качестве параметра шаблона в специализации этого класса [CWindowImpl](../../atl/reference/cwindowimpl-class.md) или другой классов окон ATL, чтобы указать минимальный набор стандартные и расширенные стили, используемые для экземпляров этого класса окна.  
  
 Используйте специализации этого шаблона, если вы хотите убедиться, что определенные стили заданы для всех экземпляров класса окна пока разрешен другие стили, задаваемый для каждого отдельного экземпляра в вызове [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create).  
  
 Если вы хотите предоставить по умолчанию стили окна, которые будут использоваться только в том случае, когда другие стили не указаны в вызове `CWindowImpl::Create`, используйте [CWinTraits](../../atl/reference/cwintraits-class.md) вместо.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="getwndstyle"></a>CWinTraitsOR::GetWndStyle  
 Эта функция вызывается для получения стандартных стилей сочетания (с помощью оператора логического или) `CWinTraits` объекта и стили по умолчанию, указанные для `t_dwStyle`.  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Стили, используемые для создания окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сочетание стили, которые передаются в `dwStyle` и те, заданные по умолчанию `t_dwStyle`, с помощью оператора логического или.  
  
##  <a name="getwndexstyle"></a>CWinTraitsOR::GetWndExStyle  
 Эта функция вызывается для получения расширенных стилей сочетания (с помощью оператора логического или) `CWinTraits` объекта и стили по умолчанию, указанные для `t_dwStyle`.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExStyle`  
 Расширенные стили, используемые для создания окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сочетание расширенных стилей, которые передаются в `dwExStyle` и по умолчанию те заданные `t_dwExStyle`, с помощью логического оператора OR  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Основные сведения о характеристик окна](../../atl/understanding-window-traits.md)


