---
title: srand | Документы Майкрософт
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
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
ms.workload:
- cplusplus
ms.openlocfilehash: e2b527561e312ce9c50dce106a243d7e49a1d303
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32406892"
---
# <a name="srand"></a>srand

Задает начальное значение начальное значение для генератора псевдослучайных чисел, используемый **rand** функции.

## <a name="syntax"></a>Синтаксис

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>Параметры

*Начальное значение* начальное значение для создания псевдослучайных чисел.

## <a name="remarks"></a>Примечания

**Srand** функция задает начальную точку для создания серии псевдослучайных целых чисел в текущем потоке. Чтобы повторно инициализировать генератор для создания той же последовательности результаты, вызовите **srand** функцией и используйте тот же *начальное значение* аргумент еще раз. Любое другое значение для *начальное значение* задает генератор на разных начальную точку в псевдослучайной последовательности. **функция RAND** извлекает псевдослучайных чисел, которые создаются. Вызов **rand** перед вызовом любого метода **srand** приводит к возникновению ошибки той же последовательности, что и вызов метода **srand** с *начальное значение* передан как 1.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**srand**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [rand](rand.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[rand](rand.md)<br/>
