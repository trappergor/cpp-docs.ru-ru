---
title: inject_statement | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inject_statement
dev_langs:
- C++
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb4142b742ae6c2a758c2a2fb5e09c604959433f
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42541646"
---
# <a name="injectstatement"></a>inject_statement
**Конкретных C++**  
  
Вставляет свой аргумент как исходный текст в заголовок библиотеки типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
inject_statement("source_text")  
```  
  
### <a name="parameters"></a>Параметры  
*source_text*  
Исходный текст, вставляемый в файл заголовка библиотеки типов.  
  
## <a name="remarks"></a>Примечания  
 
Текст вставляется в начало объявления пространства имен, в которое помещается содержимое библиотеки типов в файле заголовка.  
  
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
[директива #import](../preprocessor/hash-import-directive-cpp.md)