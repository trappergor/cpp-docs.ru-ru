---
title: "ИМЯ (C/C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: name
dev_langs: C++
helpviewer_keywords: NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 46bbbef9df3f68f322196962042039b32b4e0113
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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