---
title: Использование макроса NMAKE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6bf098a3723aa7b067b8192bf503975998e4e98
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380580"
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