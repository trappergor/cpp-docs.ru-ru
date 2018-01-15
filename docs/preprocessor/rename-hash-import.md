---
title: "Переименование (#import) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Rename
dev_langs: C++
helpviewer_keywords: rename attribute
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fe5efd48867d5911a6512c32c3e91d80201d03ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="rename-import"></a>rename (#import)
**Конкретных C++**  
  
 Обходит проблемы конфликтов имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
rename("OldName","NewName")  
```  
  
#### <a name="parameters"></a>Параметры  
 `OldName`  
 Старое имя в библиотеке типов.  
  
 `NewName`  
 Имя, используемое вместо старого имени.  
  
## <a name="remarks"></a>Примечания  
 Если этот атрибут указан, компилятор заменяет все вхождения *OldName* в библиотеку типов с помощью предоставляемого пользователем *NewName* в результирующих файлах заголовка.  
  
 Этот атрибут может использоваться, если имя в библиотеке типов совпадает с определением макроса в системных файлах заголовка. Если такой ситуации не будет устранена, то будет создан различные синтаксические ошибки, такие как [Ошибка компилятора C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) и [Ошибка компилятора C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md).  
  
> [!NOTE]
>  Замена предоставляется для имени, используемого в библиотеке типов, а не для имени, используемого в открывшемся файле заголовка.  
  
 Например, предположим, что свойство `MyParent` существует в библиотеке типов, а макрос `GetMyParent` определен в файле заголовка и используется перед `#import`. Поскольку `GetMyParent` — имя по умолчанию функции-оболочки для обработки ошибок **получить** свойство, возникнет конфликт имен. Для решения проблемы используйте следующий атрибут в инструкции `#import`:  
  
```  
rename("MyParent","MyParentX")  
```  
  
 чтобы переименовать имя `MyParent` в библиотеке типов. Попытка переименовать программу-оболочку `GetMyParent` завершится ошибкой:  
  
```  
rename("GetMyParent","GetMyParentX")  
```  
  
 Это происходит потому, что имя `GetMyParent` может возникать только в открывшемся файле заголовка библиотеки типов.  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)