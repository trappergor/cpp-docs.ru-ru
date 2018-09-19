---
title: HUGE_VAL _HUGE | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _HUGE
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _HUGE
- HUGE_VAL
dev_langs:
- C++
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9917d614261afaffe28ea92f913799c429a9611
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060724"
---
# <a name="hugeval-huge"></a>HUGE_VAL, _HUGE

## <a name="syntax"></a>Синтаксис

```

#include <math.h>

```

## <a name="remarks"></a>Примечания

`HUGE_VAL` является максимальным представимым значением double. Это значение возвращается многими математическими функциями времени выполнения при возникновении ошибки. Для некоторых функций возвращается значение –`HUGE_VAL`. `HUGE_VAL` определяется как `_HUGE`, но математические функции времени выполнения возвращают `HUGE_VAL`. Для согласованности в коде также необходимо использовать значение `HUGE_VAL`.

## <a name="see-also"></a>См. также

[Глобальные константы](../c-runtime-library/global-constants.md)