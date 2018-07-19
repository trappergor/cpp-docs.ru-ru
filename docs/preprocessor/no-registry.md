---
title: no_registry | Документы Microsoft
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
ms.openlocfilehash: 416663592f4362c110637fb4d4b4b418d9776cde
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849669"
---
# <a name="noregistry"></a>no_registry
Атрибут `no_registry` сообщает компилятору, что не следует искать в реестре библиотеки типов, импортированные с помощью директивы `#import`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#import filename no_registry  
```  
  
#### <a name="parameters"></a>Параметры  
 *filename*  
 Библиотека типов.  
  
## <a name="remarks"></a>Примечания  
 Если к указанной библиотеке типов не найден в каталоги include, компиляция завершается ошибкой, даже если библиотека типов находится в реестре.  `no_registry` распространяется и на других библиотеках типов, которые неявно импортированы с `auto_search`.  
  
 Компилятор никогда не ищет в реестре библиотеки типов, указанные по имени файла и переданные непосредственно в директиву `#import`.  
  
 Если указан атрибут `auto_search`, создаются дополнительные директивы `#import` с настройкой атрибута `no_registry` из исходной директивы `#import` (если исходная директива `#import` имела атрибут `no_registry`, созданная атрибутом `auto_search` директива `#import` также будет иметь атрибут `no_registry`).  
  
 `no_registry` полезно, если вы хотите импортировать библиотеках перекрестного типов без риска компилятору поиск более старой версии файла в реестре.  `no_registry` также полезно, если библиотека типов не зарегистрирована.  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)