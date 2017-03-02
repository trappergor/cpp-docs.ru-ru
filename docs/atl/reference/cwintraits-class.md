---
title: "Класс CWinTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinTraits
- CMDIChildWinTraits
- ATL.CWinTraits
- CFrameWinTraits
- ATL::CWinTraits
- CControlWinTraits
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
caps.latest.revision: 19
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
ms.openlocfilehash: abd62b916f976721bf85fc4bb2a94ffaf5b217ea
ms.lasthandoff: 02/24/2017

---
# <a name="cwintraits-class"></a>Класс CWinTraits
Этот класс предоставляет метод для стандартизации стили, используемые при создании объекта окна.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```  
  
#### <a name="parameters"></a>Параметры  
 `t_dwStyle`  
 Стандартное окно Стили по умолчанию.  
  
 `t_dwExStyle`  
 По умолчанию расширенные стили окна.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(Статический) Извлекает расширенные стили для `CWinTraits` объекта.|  
|[CWinTraits::GetWndStyle](#getwndstyle)|(Статический) Получает стандартный стили `CWinTraits` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Это [характеристик окна](../../atl/understanding-window-traits.md) класс предоставляет простой способ для стандартизации стили, используемые для создания объекта окна ATL. Использование в качестве параметра шаблона в специализации этого класса [CWindowImpl](../../atl/reference/cwindowimpl-class.md) или другой классов окон ATL для указания по умолчанию стандартные и расширенные стили, используемые для экземпляров этого класса окна.  
  
 Используйте этот шаблон, если нужно предоставить по умолчанию стили окна, которые будут использоваться только в том случае, когда другие стили не указаны в вызове [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create).  
  
 Библиотека ATL предоставляет три предопределенные специализации этого шаблона для часто используемых сочетаний стили окна:  
  
 `CControlWinTraits`  
 Предназначены для стандартного элемента управления окна. Используются следующие стандартные стили: **WS_CHILD**, **WS_VISIBLE**, **WS_CLIPCHILDREN**, и **WS_CLIPSIBLINGS**. Существует не расширенные стили.  
  
 `CFrameWinTraits`  
 Предназначены для стандартных фрейма окна. Стандартные стили, используемые включают: **WS_OVERLAPPEDWINDOW**, **WS_CLIPCHILDREN**, и **WS_CLIPSIBLINGS**. Включить расширенные стили, используемые: **WS_EX_APPWINDOW** и **WS_EX_WINDOWEDGE**.  
  
 `CMDIChildWinTraits`  
 Предназначен для стандартных дочернего окна MDI. Стандартные стили, используемые включают: **WS_OVERLAPPEDWINDOW**, **WS_CHILD**, **WS_VISIBLE**, **WS_CLIPCHILDREN**, и **WS_CLIPSIBLINGS**. Включить расширенные стили, используемые: **WS_EX_MDICHILD**.  
  
 Если вы хотите убедиться, что определенные стили устанавливаются для всех экземпляров класса окна пока разрешен другие стили, чтобы задать отдельно для каждого экземпляра, используйте [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) вместо.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="a-namegetwndstylea--cwintraitsgetwndstyle"></a><a name="getwndstyle"></a>CWinTraits::GetWndStyle  
 Эта функция вызывается для получения стандартных стилей `CWinTraits` объекта.  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Стандартные стили, используемые для создания окна. Если `dwStyle` равно 0, значения стиля шаблона ( `t_dwStyle`) возвращаются. Если `dwStyle` не равно нулю, `dwStyle` возвращается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное окно Стили объекта.  
  
##  <a name="a-namegetwndexstylea--cwintraitsgetwndexstyle"></a><a name="getwndexstyle"></a>CWinTraits::GetWndExStyle  
 Эта функция вызывается для получения расширенных стилей `CWinTraits` объекта.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExStyle`  
 Расширенные стили, используемые для создания окна. Если `dwExStyle` равно 0, значения стиля шаблона ( `t_dwExStyle`) возвращаются. Если `dwExStyle` не равно нулю, `dwExStyle` возвращается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расширенные стили окна объекта.  
  
## <a name="see-also"></a>См. также  
 [Члены класса](http://msdn.microsoft.com/en-us/dbe6a147-3f01-4aea-a3fb-fe6ebadc31f8)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Основные сведения о характеристик окна](../../atl/understanding-window-traits.md)

