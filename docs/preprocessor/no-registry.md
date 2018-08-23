---
title: no_registry | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_registry
dev_langs:
- C++
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 105c2b0ee4d2648a1cc43d0baca9f30146184e78
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540492"
---
# <a name="noregistry"></a>no_registry
**no_registry** указывает компилятору не искать в реестре библиотеки типов, импортированные с `#import`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#import filename no_registry  
```  
  
### <a name="parameters"></a>Параметры  
*filename*  
Библиотека типов.  
  
## <a name="remarks"></a>Примечания  
 
Если указанная библиотека типов не найден в каталогах включения, компиляция завершается ошибкой, даже если библиотека типов находится в реестре.  **no_registry** распространяет на другие библиотеки типов, неявно импортированные с использованием `auto_search`.  
  
Компилятор никогда не ищет в реестре библиотеки типов, указанные по имени файла и переданные непосредственно в директиву `#import`.  
  
При `auto_search` указано, дополнительный `#import`s будет создана с **no_registry** задание начального `#import` (если начального `#import` директиву **no_registry** , `auto_search`-созданный `#import` также **no_registry**.)  
  
**no_registry** полезно, если вы хотите импортировать кросс-библиотеках типов без риска, что компилятор найдет более старой версии файла в реестре. **no_registry** также полезен, если библиотека типов не зарегистрирована.  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
[директива #import](../preprocessor/hash-import-directive-cpp.md)