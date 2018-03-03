---
title: "Класс CAtlFileMapping | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2dce8e219c2a64ecc6e9b307533ecc0ea11d2792
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlFileMapping::operator T *](#operator_t_star)|Разрешает неявные преобразования `CAtlFileMapping` объектов `T`  **\*** .|  
  
## <a name="remarks"></a>Примечания  
 Этот класс добавляет оператор один приведения, чтобы разрешить неявные преобразования `CAtlFileMapping` объектов `T`  **\*** . Предоставленные другим членам базового класса, [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlfile.h  
  
##  <a name="operator_t_star"></a>CAtlFileMapping::operator T *  
 Разрешает неявные преобразования `CAtlFileMapping` объектов `T`  **\*** .  
  
```  
operator T*() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `T`  **\***  указатель в начале файла размещенный в памяти.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) и повторно интерпретирует возвращенный указатель как `T`  **\***  где *T* тип, используемый в качестве шаблона параметр этого класса.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
