---
title: "no_implementation | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_implementation
dev_langs: C++
helpviewer_keywords: no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5d4c378d1d64eefe5ae641d259aa502b7e4bcf32
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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