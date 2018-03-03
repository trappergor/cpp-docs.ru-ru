---
title: "Класс CAtlAutoThreadModuleT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 082214794b2caa66e8be1127c664e0ffec18a394
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
 Класс, который реализует COM-сервера.  
  
 `ThreadAllocator`  
 Класс управления выбором потока. Значение по умолчанию — [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
 `dwWait`  
 Интервал времени ожидания в миллисекундах. Значение по умолчанию равно INFINITE, означающее интервал времени ожидания для метода никогда не истекает.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|Эта статическая функция динамически вычисляет и возвращает максимальное число потоков модуля exe-файла, в зависимости от количества процессоров.|  
  
## <a name="remarks"></a>Примечания  
 Класс [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) является производным от `CAtlAutoThreadModuleT` для реализации пула потоков, модели подразделения COM-сервера. Он заменяет устаревший класс [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
> [!NOTE]
>  Этот класс должен не использоваться в библиотеке DLL по умолчанию `dwWait` значение INFINITE приведет к взаимоблокировке, при выгрузке библиотеки DLL.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="getdefaultthreads"></a>CAtlAutoThreadModuleT::GetDefaultThreads  
 Эта статическая функция динамически вычисляет и возвращает максимальное число потоков модуля exe-файла, в зависимости от количества процессоров.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число потоков, создаваемых в модуле exe-файла.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если вы хотите использовать другой метод для подсчета количества потоков. По умолчанию число потоков зависит число процессоров.  
  
## <a name="see-also"></a>См. также  
 [Класс IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)   
 [Классы модуля](../../atl/atl-module-classes.md)
