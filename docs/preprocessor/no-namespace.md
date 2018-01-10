---
title: "no_namespace | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_namespace
dev_langs: C++
helpviewer_keywords: no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6b83e60aca7ea0e39ba67834ad1def0896dcdc07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nonamespace"></a>no_namespace
**Конкретных C++**  
  
 Указывает, что пространство имен не генерируется компилятором.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
no_namespace  
```  
  
## <a name="remarks"></a>Примечания  
 Содержимое библиотеки типов в файле заголовка `#import` обычно определяется в пространстве имен. Имя пространства имен, указанное в **библиотеки** оператором в исходном файле IDL. Если атрибут `no_namespace` определен, это пространство имен не генерируется компилятором.  
  
 Если вы хотите использовать различные пространства имен, используйте [rename_namespace](../preprocessor/rename-namespace.md) атрибутом.  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)