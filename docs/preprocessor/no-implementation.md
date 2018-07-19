---
title: no_implementation | Документы Microsoft
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
ms.openlocfilehash: bf756a411404d2ebb821d5b226818844acfca75b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849552"
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
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)