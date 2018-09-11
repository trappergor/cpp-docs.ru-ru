---
title: no_namespace | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_namespace
dev_langs:
- C++
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6eded6b4d543248cc7bf53a0e4ba622b2b74c8b3
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42539661"
---
# <a name="nonamespace"></a>no_namespace
**Конкретных C++**  
  
Указывает, что пространство имен не генерируется компилятором.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
no_namespace  
```  
  
## <a name="remarks"></a>Примечания  
 
Содержимое библиотеки типов в файле заголовка `#import` обычно определяется в пространстве имен. Имя пространства имен, указанное в `library` инструкции исходного файла IDL. Если **no_namespace** атрибут указан, то это пространство имен не генерируется компилятором.  
  
Если вы хотите использовать другое имя пространства имен, используйте [rename_namespace](../preprocessor/rename-namespace.md) атрибутом.  
  
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
[директива #import](../preprocessor/hash-import-directive-cpp.md)