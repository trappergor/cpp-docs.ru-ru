---
title: "Использование макроса NMAKE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9893e7ec1ba29b4b5ed2ccb569a135f44b2ed47f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="using-an-nmake-macro"></a>Использование макроса NMAKE
Чтобы использовать макрос, имя необходимо заключите в круглые скобки, предшествует знак доллара ($).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
$(macroname)  
```  
  
## <a name="remarks"></a>Примечания  
 Пробелы не допускаются. Скобки являются необязательными при *имя макроса* — это отдельный символ. Строка определения заменяет $(*имя макроса*); неопределенный макрос заменяется на пустую строку.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
 [Макроподстановка](../build/macro-substitution.md)  
  
## <a name="see-also"></a>См. также  
 [Макросы и программа NMAKE](../build/macros-and-nmake.md)