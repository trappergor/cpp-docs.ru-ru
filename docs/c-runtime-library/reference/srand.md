---
title: "srand | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- srand
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- srand
dev_langs:
- C++
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
ms.assetid: 7bf56dc5-5692-4182-a3c1-18af98d2dd1a
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: e86ea8aa561af584a6825d4225820aca7baeced2
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="srand"></a>srand
Задает начальное значение для генератора псевдослучайных чисел.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void srand(  
   unsigned int seed   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `seed`  
 Начальное значение для создания псевдослучайных чисел  
  
## <a name="remarks"></a>Примечания  
 Функция `srand` задает начальную точку для создания ряда псевдослучайных целых чисел в текущем потоке. Для повторной инициализации генератора для создания результатов той же последовательности результатов вызовите функцию `srand` и использовать тот же аргумент `seed`. Любое другое значение для `seed` задает для генератора другую начальную точку создания последовательности псевдослучайных чисел. `rand` возвращает созданные псевдослучайные числа. Вызов `rand`, предшествующий вызову `srand`, создает ту же последовательность, что и вызов `srand` с `seed`, переданный в качестве 1.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`srand`|\<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для [rand](../../c-runtime-library/reference/rand.md).  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [rand](../../c-runtime-library/reference/rand.md)
