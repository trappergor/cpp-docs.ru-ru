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
ms.openlocfilehash: 7972ddfe6ae9c1d591bdbd4cc5e208d78e826037
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107560"
---
# <a name="srand"></a>srand

Задает начальное значение для генератора псевдослучайных чисел, используемый **rand** функции.

## <a name="syntax"></a>Синтаксис

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>Параметры

*Начальное значение*<br/>
Начальное значение для создания псевдослучайных чисел

## <a name="remarks"></a>Примечания

**Srand** функция задает начальную точку для создания ряда псевдослучайных целых чисел в текущем потоке. Для повторной инициализации генератора для создания результатов той же последовательности, вызовите **srand** работать и использовать тот же *начальное значение* аргумент еще раз. Любое другое значение для *начальное значение* задает генератора другую начальную точку создания последовательности псевдослучайных чисел. **функция RAND** извлекает псевдослучайных чисел, которые создаются. Вызов **rand** предшествующий вызову **srand** создает ту же последовательность, что и вызов метода **srand** с *начальное значение* переданный в качестве 1.

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
