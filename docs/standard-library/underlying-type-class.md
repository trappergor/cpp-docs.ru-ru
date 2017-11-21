---
title: "Класс underlying_type | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_traits/std::underlying_type
dev_langs: C++
helpviewer_keywords: underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b539f62e1e9c6b9bf11b176bd50f7dca63508ddd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="underlyingtype-class"></a>Класс underlying_type
Создает базовый целочисленный тип для типа перечисления.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
struct underlying_type;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип для изменения.  
  
## <a name="remarks"></a>Примечания  
 Определение типа члена `type` для класса шаблона задает имя базового целочисленного типа `T`, где `T` имеет тип перечисления, в противном случае определение типа члена `type` отсутствует.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)



