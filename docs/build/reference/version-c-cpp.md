---
title: ВЕРСИЯ (C/C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VERSION
dev_langs:
- C++
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fcaf4e113af6182a2d3d735e4c668b62336e2c79
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="version-cc"></a>VERSION (C/C++)
Указывает ССЫЛКУ, чтобы поместить число в заголовке файла .exe или DLL.  
  
```  
VERSION major[.minor]  
```  
  
## <a name="remarks"></a>Примечания  
 *Основных* и *дополнительный* аргументами являются десятичные числа в диапазоне от 0 до 65 535. Значение по умолчанию используется версия 0.0.  
  
 Можно указать номер версии — с [сведения о версии](../../build/reference/version-version-information.md) (или версия) параметра.  
  
## <a name="see-also"></a>См. также  
 [Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)