---
title: Класс CWinTraits | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea1eafc6376c44a09d13fb513d41f222048708d9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362512"
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
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(Статический) Извлекает расширенные стили для `CWinTraits` объекта.|  
|[CWinTraits::GetWndStyle](#getwndstyle)|(Статический) Получает стандартный стили для `CWinTraits` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Это [признаки окна](../../atl/understanding-window-traits.md) класс предоставляет простой способ для стандартизации стили, используемые для создания объекта ATL окна. Использовать специализации этого класса в качестве параметра шаблона для [CWindowImpl](../../atl/reference/cwindowimpl-class.md) той или иной классов окон ATL Чтобы задать по умолчанию стандартные и расширенные стили, используемые для экземпляров этого класса окна.  
  
 Используйте этот шаблон, когда вы хотите предоставить по умолчанию стили окна, которые будут использоваться только в том случае, если нет другие стили, указаны в вызове [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create).  
  
 Библиотека ATL предоставляет три стандартных специализации этого шаблона для часто используемых сочетаний стили окна:  
  
 `CControlWinTraits`  
 Предназначены для окна стандартного элемента управления. Используются следующие стандартные стили: **WS_CHILD**, **WS_VISIBLE**, **WS_CLIPCHILDREN**, и **WS_CLIPSIBLINGS**. Нет не расширенные стили.  
  
 `CFrameWinTraits`  
 Предназначены для стандартной фрейм окна. Включают стандартные стили, используемые: **WS_OVERLAPPEDWINDOW**, **WS_CLIPCHILDREN**, и **WS_CLIPSIBLINGS**. Включить расширенные стили, используемые: **WS_EX_APPWINDOW** и **WS_EX_WINDOWEDGE**.  
  
 `CMDIChildWinTraits`  
 Предназначены для стандартной дочернего окна MDI. Включают стандартные стили, используемые: **WS_OVERLAPPEDWINDOW**, **WS_CHILD**, **WS_VISIBLE**, **WS_CLIPCHILDREN**и **WS_CLIPSIBLINGS**. Включить расширенные стили, используемые: **WS_EX_MDICHILD**.  
  
 Если вы хотите убедиться, что определенные стили для всех экземпляров класса окна, пока разрешен другие стили, чтобы задать для каждого отдельного экземпляра, используйте [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) вместо него.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="getwndstyle"></a>  CWinTraits::GetWndStyle  
 Эта функция вызывается для получения стандартных стилей `CWinTraits` объекта.  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Стандартные стили, используемые для создания окна. Если `dwStyle` равно 0, значения стиля шаблона ( `t_dwStyle`) возвращаются. Если `dwStyle` отлично от нуля, `dwStyle` возвращается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стили стандартного окна объекта.  
  
##  <a name="getwndexstyle"></a>  CWinTraits::GetWndExStyle  
 Эта функция вызывается для получения расширенных стилей `CWinTraits` объекта.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExStyle`  
 Расширенные стили, используемые для создания окна. Если `dwExStyle` равно 0, значения стиля шаблона ( `t_dwExStyle`) возвращаются. Если `dwExStyle` отлично от нуля, `dwExStyle` возвращается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расширенные стили окна объекта.  
  
## <a name="see-also"></a>См. также  
 [Члены класса](http://msdn.microsoft.com/en-us/dbe6a147-3f01-4aea-a3fb-fe6ebadc31f8)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Основные сведения о характеристиках окна](../../atl/understanding-window-traits.md)
