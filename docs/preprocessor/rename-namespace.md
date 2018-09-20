---
title: rename_namespace | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rename_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7608255b5369443ce1045f896b776cb283fdb1cb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411863"
---
# <a name="renamenamespace"></a>rename_namespace
**Конкретных C++**  
  
Переименовывает пространство имен, к которому относится содержимое библиотеки типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
rename_namespace("NewName")  
```  
  
### <a name="parameters"></a>Параметры  
*NewName*  
Новое имя пространства имен.  
  
## <a name="remarks"></a>Примечания  
 
Он принимает один аргумент, *NewName*, который задает новое имя для пространства имен.  
  
Чтобы удалить пространство имен, используйте [no_namespace](../preprocessor/no-namespace.md) атрибутом.  
  
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)