---
title: _fmode | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- fmode
- _fmode
dev_langs:
- C++
helpviewer_keywords:
- file translation [C++], default mode
- fmode function
- _fmode function
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9dfb5343e7a9ab64b2a1bd5cdb6edea0821e1559
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32390126"
---
# <a name="fmode"></a>_fmode
Переменная `_fmode` устанавливает режим преобразования файлов по умолчанию — преобразование текстовых значений в двоичные и наоборот. Использование этой глобальной переменной не рекомендуется в силу наличия более безопасных функциональных версий [_get_fmode](../c-runtime-library/reference/get-fmode.md) и [_set_fmode](../c-runtime-library/reference/set-fmode.md), которые должны использоваться вместо глобальной переменной. Об этом объявляется в файле Stdlib.h описанным ниже образом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
extern int _fmode;  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию параметр `_fmode` для преобразования в текстовом режиме имеет значение `_O_TEXT`. Для двоичного режима используется параметр `_O_BINARY`.  
  
 Значение `_fmode` можно изменить тремя указанными ниже способами.  
  
-   Связь с Binmode.obj. Изменяет начальное значение параметра `_fmode` на `_O_BINARY`, в результате чего все файлы, кроме `stdin`, `stdout` и `stderr`, открываются в двоичном режиме.  
  
-   Вызовите `_get_fmode` или `_set_fmode`, чтобы соответственно получить или задать глобальную переменную `_fmode`.  
  
-   Измените значение `_fmode` напрямую, задав его в своей программе.  
  
## <a name="see-also"></a>См. также  
 [Глобальные переменные](../c-runtime-library/global-variables.md)   
 [_get_fmode](../c-runtime-library/reference/get-fmode.md)   
 [_set_fmode](../c-runtime-library/reference/set-fmode.md)