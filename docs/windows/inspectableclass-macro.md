---
title: Макрос InspectableClass | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
dev_langs:
- C++
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 922f7f74771125aed0122c408ef902da2569e5c7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873775"
---
# <a name="inspectableclass-macro"></a>Макрос InspectableClass
Задает уровень имя и доверия класса среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
InspectableClass(  
   runtimeClassName,   
   trustLevel)  
```  
  
#### <a name="parameters"></a>Параметры  
 `runtimeClassName`  
 Полное текстовое имя класса среды выполнения.  
  
 `trustLevel`  
 Один из [TrustLevel](http://msdn.microsoft.com/library/br224625.aspx) значений перечисления.  
  
## <a name="remarks"></a>Примечания  
 `InspectableClass` Макрос может использоваться только с типами среды выполнения Windows.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс RuntimeClass](../windows/runtimeclass-class.md)