---
title: "Класс CAtlFileMapping | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlFileMapping<T>
- ATL.CAtlFileMapping
- ATL::CAtlFileMapping
- CAtlFileMapping
- ATL.CAtlFileMapping<T>
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 2693647af904eab1ed0f84bc406bc1207d4a9b8c
ms.lasthandoff: 02/24/2017

---
# <a name="catlfilemapping-class"></a>Класс CAtlFileMapping
Этот класс представляет размещенный в памяти файл, добавление оператора приведения для методов [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
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
  
## <a name="members"></a>Члены  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlFileMapping::operator T *](#operator_t_star)|Допускается явное преобразование `CAtlFileMapping` объектов `T` ** \* **.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс добавляет оператора приведения одного, чтобы разрешить неявные преобразования `CAtlFileMapping` объектов `T` ** \* **. Предоставленные другие члены базового класса, [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlfile.h  
  
##  <a name="a-nameoperatortstara--catlfilemappingoperator-t"></a><a name="operator_t_star"></a>CAtlFileMapping::operator T *  
 Допускается явное преобразование `CAtlFileMapping` объектов `T` ** \* **.  
  
```  
operator T*() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `T` ** \* ** указатель в начале файла размещенный в памяти.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) и повторно интерпретирует возвращаемого указателя как `T` ** \* ** где *T* — тип, используемый в качестве параметра шаблона этого класса.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

