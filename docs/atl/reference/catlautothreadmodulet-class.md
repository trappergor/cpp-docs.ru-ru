---
title: "Класс CAtlAutoThreadModuleT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CAtlAutoThreadModuleT
- ATL::CAtlAutoThreadModuleT
- CAtlAutoThreadModuleT
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 86b35f0a6a3ab43c170ee710838ec9ba0e2fc5b0
ms.lasthandoff: 02/24/2017

---
# <a name="catlautothreadmodulet-class"></a>Класс CAtlAutoThreadModuleT
Этот класс предоставляет методы для реализации пула потоков, модели подразделения COM-сервера.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T, 
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, который будет реализовывать COM-сервера.  
  
 `ThreadAllocator`  
 Класс выбора потока управления. Значение по умолчанию — [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
 `dwWait`  
 Задает интервал времени ожидания в миллисекундах. Значение по умолчанию равно INFINITE, означающее интервал времени ожидания метод никогда не истекает.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|Эта статическая функция динамически вычисляет и возвращает максимальное количество потоков для модуля exe-файла, в зависимости от количества процессоров.|  
  
## <a name="remarks"></a>Примечания  
 Класс [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) является производным от `CAtlAutoThreadModuleT` для реализации пула потоков, модели подразделения COM-сервера. Он заменяет устаревший класс [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
> [!NOTE]
>  Этот класс должен не использоваться в библиотеке DLL, по умолчанию `dwWait` значение INFINITE вызовет взаимоблокировку при выгрузке библиотеки DLL.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="a-namegetdefaultthreadsa--catlautothreadmoduletgetdefaultthreads"></a><a name="getdefaultthreads"></a>CAtlAutoThreadModuleT::GetDefaultThreads  
 Эта статическая функция динамически вычисляет и возвращает максимальное количество потоков для модуля exe-файла, в зависимости от количества процессоров.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число потоков, создаваемых в модуле exe-файла.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если вы хотите использовать другой метод для подсчета количества потоков. По умолчанию число потоков, основан на число процессоров.  
  
## <a name="see-also"></a>См. также  
 [Класс IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)   
 [Классы модуля](../../atl/atl-module-classes.md)

