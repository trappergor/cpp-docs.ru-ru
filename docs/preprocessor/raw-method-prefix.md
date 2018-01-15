---
title: "raw_method_prefix | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: raw_method_prefix
dev_langs: C++
helpviewer_keywords: raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f140bf7d65f620552dea9f2d25f4ae472139b98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="rawmethodprefix"></a>raw_method_prefix
**Конкретных C++**  
  
 Указывает другой префикс, чтобы избежать конфликтов имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
raw_method_prefix("Prefix")  
```  
  
#### <a name="parameters"></a>Параметры  
 `Prefix`  
 Необходимый префикс.  
  
## <a name="remarks"></a>Примечания  
 Низкоуровневые свойства и методы предоставляются функциями-членами с именами с префиксом по умолчанию **raw_** во избежание конфликтов имен с помощью функции-члены высокого уровня обработки ошибок.  
  
> [!NOTE]
>  Эффекты `raw_method_prefix` атрибута не будут изменены наличием [raw_interfaces_only](#_predir_raw_interfaces_only) атрибута. `raw_method_prefix` всегда имеет приоритет над `raw_interfaces_only` в определении префикса. Если оба атрибута используются в одном и том же операторе `#import`, используется префикс, определяемый атрибутом `raw_method_prefix`.  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)