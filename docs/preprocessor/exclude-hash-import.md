---
title: исключить (#import) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- exclude
dev_langs:
- C++
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5798c7515c411b9abf9d10229a6185e01bb92f7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400202"
---
# <a name="exclude-import"></a>exclude (#import)
**Конкретных C++**  
  
Исключает элементы из создаваемых файлов заголовка библиотеки типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
exclude("Name1"[, "Name2",...])  
```  
  
### <a name="parameters"></a>Параметры  
*Name1*  
Первый исключаемый элемент.  
  
*Имя 2*  
Второй исключаемый элемент (при необходимости).  
  
## <a name="remarks"></a>Примечания  
 
Библиотеки типов могут содержать определения элементов, которые определены в системных заголовочных файлах или других библиотеках типов. Этот атрибут может принимать любое количество аргументов, каждый из которых является именем исключаемого элемента, находящегося на верхнем уровне библиотеки типов.  
  
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)