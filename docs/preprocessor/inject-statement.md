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
ms.openlocfilehash: bb3bdc2b4e00cd9e2167adeb0ad7d3023af9eb2e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384212"
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
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)