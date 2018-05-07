---
title: ИМЯ (C/C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- name
dev_langs:
- C++
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a94b82a65cf68d9802d7bf9620e4128ab6b35071
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="name-cc"></a>NAME (C/C++)
Указывает имя основного выходного файла.  
  
```  
NAME [application][BASE=address]  
```  
  
## <a name="remarks"></a>Примечания  
 Можно указать имя выходного файла — с [/OUT](../../build/reference/out-output-file-name.md) компоновщика и можно задать базовый адрес осуществляется с [/BASE](../../build/reference/base-base-address.md) компоновщика. Если указаны оба/OUT переопределяет **имя**.  
  
 При создании библиотеки DLL, имя будет влияют только на имя библиотеки DLL.  
  
## <a name="see-also"></a>См. также  
 [Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)