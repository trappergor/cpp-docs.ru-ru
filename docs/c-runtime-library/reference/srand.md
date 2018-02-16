---
title: "srand | Документы Майкрософт"
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4cc76b80ca6c01d6512c69cc13fb0934e79b6ae5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="srand"></a>srand

Задает начальное значение начальное значение для генератора псевдослучайных чисел, используемый `rand` функции.

## <a name="syntax"></a>Синтаксис

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>Параметры

*seed*  
Начальное значение для создания псевдослучайных чисел

## <a name="remarks"></a>Примечания

Функция `srand` задает начальную точку для создания ряда псевдослучайных целых чисел в текущем потоке. Чтобы повторно инициализировать генератор для создания той же последовательности результаты, вызовите `srand` функцией и используйте тот же *начальное значение* аргумент еще раз. Любое другое значение для *начальное значение* задает генератор на разных начальную точку в псевдослучайной последовательности. `rand` возвращает созданные псевдослучайные числа. Вызов `rand` перед вызовом любого метода `srand` приводит к возникновению ошибки той же последовательности, что и вызов метода `srand` с *начальное значение* передан как 1.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`srand`|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.

## <a name="example"></a>Пример

См. пример для [rand](../../c-runtime-library/reference/rand.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)  
[rand](../../c-runtime-library/reference/rand.md)  
