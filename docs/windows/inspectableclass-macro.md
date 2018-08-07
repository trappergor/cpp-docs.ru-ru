---
title: Макрос InspectableClass | Документация Майкрософт
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
ms.openlocfilehash: a02e20f2b87afc312c24683417f808d636c2757f
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608960"
---
# <a name="inspectableclass-macro"></a>Макрос InspectableClass
Задает уровень имя и доверия класса среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
InspectableClass(  
   runtimeClassName,   
   trustLevel)  
```  
  
### <a name="parameters"></a>Параметры  
 *runtimeClassName*  
 Полное текстовое имя класса среды выполнения.  
  
 *trustLevel*  
 Один из [TrustLevel](http://msdn.microsoft.com/library/br224625.aspx) значений перечисления.  
  
## <a name="remarks"></a>Примечания  
 **InspectableClass** макрос может использоваться только с типами среды выполнения Windows.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс RuntimeClass](../windows/runtimeclass-class.md)