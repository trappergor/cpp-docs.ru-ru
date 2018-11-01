---
title: Предупреждение компилятора (уровень 1) C4612
ms.date: 08/27/2018
f1_keywords:
- C4612
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
ms.openlocfilehash: ed5458fc52c1c9c9f12187095e4658204613d1a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574269"
---
# <a name="compiler-warning-level-1-c4612"></a>Предупреждение компилятора (уровень 1) C4612

> ошибка в имени включаемого файла

## <a name="remarks"></a>Примечания

Это предупреждение возникает с **#pragma include_alias** , когда имя файла указано неправильно или отсутствует.

Аргументы для **#pragma include_alias** инструкции можно использовать в форме предложения (»*filename*«) или форму с угловыми (\<*filename*>), но обе должны Используйте ту же форму.

## <a name="example"></a>Пример

```cpp
// C4612.cpp
// compile with: /W1 /LD
#pragma include_alias("StandardIO", <stdio.h>) // C4612
```