---
title: "no_smart_pointers | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_search_pointers
dev_langs: C++
helpviewer_keywords: no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: efa69bf3b0ae770bcd4a29c7430b5b21677b453e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nosmartpointers"></a>no_smart_pointers
**Конкретных C++**  
  
 Отключает создание интеллектуальных указателей для всех интерфейсов в библиотеке типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
no_smart_pointers  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию при использовании директивы `#import` пользователь получает объявление интеллектуального указателя для всех интерфейсов в библиотеке типов. Эти интеллектуальные указатели имеют тип [класс _com_ptr_t](../cpp/com-ptr-t-class.md).  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)