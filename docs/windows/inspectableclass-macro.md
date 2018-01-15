---
title: "Макрос InspectableClass | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::InspectableClass
dev_langs: C++
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1ac1f84c76bb61d24ee25e8ca431e13620f6f85a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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