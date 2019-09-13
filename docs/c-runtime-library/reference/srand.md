---
title: srand
ms.date: 01/02/2018
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- srand
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
ms.openlocfilehash: d74ae4cbec5a76df48bb2b56acab7329e6cf8aa5
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927403"
---
# <a name="srand"></a>srand

Задает начальное начальное значение для генератора номеров псевдослучайное, используемого функцией **Rand** .

## <a name="syntax"></a>Синтаксис

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>Параметры

*инициализировать*<br/>
Начальное значение для создания псевдослучайных чисел

## <a name="remarks"></a>Примечания

Функция **srand** задает начальную точку для создания последовательности целых чисел псевдослучайное в текущем потоке. Чтобы повторно инициализировать генератор для создания той же последовательности результатов, вызовите функцию **srand** и снова используйте один и тот же аргумент *начального значения* . Любое другое значение *начального* значения задает генератору другую начальную точку в последовательности псевдослучайное. **Rand** извлекает созданные номера псевдослучайное. Вызов **функции RAND** перед любым вызовом **srand** создает ту же последовательность, что и вызов **srand** с *начальным* значением, переданным как 1.

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
