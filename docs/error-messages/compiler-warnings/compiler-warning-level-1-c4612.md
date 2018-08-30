---
title: Предупреждение компилятора (уровень 1) C4612 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4612
dev_langs:
- C++
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10a0a5640386f5e5673f39d6c2c76ee18fcc7ba7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210734"
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