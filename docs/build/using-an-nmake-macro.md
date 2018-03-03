---
title: "Использование макроса NMAKE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc5c6c8851654b1a767967ffc900886d75521130
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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