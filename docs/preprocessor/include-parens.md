---
title: Метод Include() | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- include()
dev_langs:
- C++
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ebadd9e453e8a34e92acee363d0dd6b6ff765910
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42538906"
---
# <a name="include"></a>include()
**Конкретных C++**  
  
Отключает автоматическое исключение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
include("Name1"[,"Name2", ...])  
```  
  
### <a name="parameters"></a>Параметры  
*Name1*  
Первый элемент для принудительного включения.  
  
*Имя 2*  
Второй элемент для принудительного включения (при необходимости).  
  
## <a name="remarks"></a>Примечания  
 
Библиотеки типов могут содержать определения элементов, которые определены в системных заголовочных файлах или других библиотеках типов. Директива `#import` пытается предотвратить ошибки об использовании нескольких определений, автоматически исключая такие элементы. Если элементы были исключены, обозначенный [Предупреждение компилятора (уровень 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md), и они не должны были, этот атрибут может использоваться для отключения автоматического исключения. Этот атрибут может принимать любое количество аргументов, каждый из которых является именем включаемого элемента библиотеки типов.  
  
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
[директива #import](../preprocessor/hash-import-directive-cpp.md)