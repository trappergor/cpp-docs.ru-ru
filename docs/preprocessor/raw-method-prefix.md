---
title: raw_method_prefix | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_method_prefix
dev_langs:
- C++
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8fb9178bc315385bab97cea473430745ad66d973
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42541278"
---
# <a name="rawmethodprefix"></a>raw_method_prefix
**Конкретных C++**  
  
Указывает другой префикс, чтобы избежать конфликтов имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
raw_method_prefix("Prefix")  
```  
  
### <a name="parameters"></a>Параметры  
*Prefix*  
Необходимый префикс.  
  
## <a name="remarks"></a>Примечания  
 
Низкоуровневые свойства и методы предоставляются функциями-членами с именами с префиксом по умолчанию **raw_** во избежание конфликтов имен с помощью функции-члены высокого уровня обработки ошибок.  
  
> [!NOTE]
> Последствия **raw_method_prefix** атрибута не изменяется при наличии [raw_interfaces_only](#_predir_raw_interfaces_only) атрибута. **Raw_method_prefix** всегда имеет приоритет над `raw_interfaces_only` в определении префикса. Если оба атрибута используются в том же `#import` инструкции, а затем префикс, определенный параметром **raw_method_prefix** используется атрибут.  
  
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
[директива #import](../preprocessor/hash-import-directive-cpp.md)