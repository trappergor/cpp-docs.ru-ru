---
title: Класс CWinTraitsOR | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
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
ms.workload:
- cplusplus
ms.openlocfilehash: ac6cf07fcd6d3703ffb6b483ba19a2d12520cb0a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|Извлекает расширенные стили для `CWinTraitsOR` объекта.|  
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|Получает стандартный стили для `CWinTraitsOR` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Это [признаки окна](../../atl/understanding-window-traits.md) класс предоставляет простой способ для стандартизации стили, используемые для создания объекта ATL окна. Использовать специализации этого класса в качестве параметра шаблона для [CWindowImpl](../../atl/reference/cwindowimpl-class.md) той или иной классов окон ATL чтобы указать минимальный набор стандартных и расширенных стилей для экземпляры этого класса окна.  
  
 Используйте этот шаблон является специализацией, чтобы убедиться, что определенные стили для всех экземпляров класса окна, пока разрешен другие стили, задаваемое для каждого отдельного экземпляра в вызове [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create).  
  
 Если вы хотите предоставить по умолчанию стили окна, которые будут использоваться только в том случае, если нет другие стили, указаны в вызове `CWindowImpl::Create`, используйте [CWinTraits](../../atl/reference/cwintraits-class.md) вместо него.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="getwndstyle"></a>CWinTraitsOR::GetWndStyle  
 Эта функция вызывается для получения сочетание (с помощью оператора логического или) стандартных стилей `CWinTraits` объекта и стили по умолчанию, указанные для `t_dwStyle`.  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Стили, используемые для создания окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сочетание стилей, которые передаются в `dwStyle` и те, заданные по умолчанию `t_dwStyle`, с помощью оператора логического или.  
  
##  <a name="getwndexstyle"></a>CWinTraitsOR::GetWndExStyle  
 Эта функция вызывается для получения сочетание (с помощью оператора логического или) расширенных стилей `CWinTraits` объекта и стили по умолчанию, указанные для `t_dwStyle`.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExStyle`  
 Расширенные стили, используемые для создания окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сочетание расширенные стили, которые передаются в `dwExStyle` и по умолчанию другие заданные `t_dwExStyle`, с помощью логического оператора OR  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Основные сведения о характеристиках окна](../../atl/understanding-window-traits.md)

