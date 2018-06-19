---
title: Класс CAtlFileMapping | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 524e5d9c7cef5bcff0d72ddf1225ef79b1b26d64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358845"
---
# <a name="catlfilemapping-class"></a>Класс CAtlFileMapping
Этот класс представляет размещенный в памяти файла, добавляя оператор приведения для методов [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T = char>  
class CAtlFileMapping : public CAtlFileMappingBase
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, используемая для оператора приведения.  
  
## <a name="members"></a>Участники  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlFileMapping::operator T *](#operator_t_star)|Разрешает неявные преобразования `CAtlFileMapping` объектов `T` **\***.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс добавляет оператор один приведения, чтобы разрешить неявные преобразования `CAtlFileMapping` объектов `T` **\***. Предоставленные другим членам базового класса, [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlfile.h  
  
##  <a name="operator_t_star"></a>  CAtlFileMapping::operator T *  
 Разрешает неявные преобразования `CAtlFileMapping` объектов `T` **\***.  
  
```  
operator T*() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `T` **\*** указатель в начале файла размещенный в памяти.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) и повторно интерпретирует возвращенный указатель как `T` **\*** где *T* тип, используемый в качестве шаблона параметр этого класса.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
