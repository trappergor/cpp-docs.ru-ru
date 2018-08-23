---
title: no_implementation | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_implementation
dev_langs:
- C++
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbf715e2cbd19d139904438e722e4d0b72e29f29
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42539479"
---
# <a name="noimplementation"></a>no_implementation
**Конкретных C++**  
  
Отключает создание заголовка .tli, который содержит реализацию функций-членов оболочки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
no_implementation  
```  
  
## <a name="remarks"></a>Примечания  
 
Если этот атрибут указан, то заголовок .tlh с объявлениями для предоставления элементов библиотеки типов создается без оператора `#include` для включения файла заголовка .tli.  
  
Этот атрибут используется в сочетании с [implementation_only](../preprocessor/implementation-only.md).  
  
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
[директива #import](../preprocessor/hash-import-directive-cpp.md)