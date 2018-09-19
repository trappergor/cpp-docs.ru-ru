---
title: Ошибка компилятора C3452 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3452
dev_langs:
- C++
helpviewer_keywords:
- C3452
ms.assetid: e5293dcf-cb70-4133-ae2a-0bb496950ba0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 392bddb57b90892bc867bcd201a99fdfc1e3f226
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118106"
---
# <a name="compiler-error-c3452"></a>Ошибка компилятора C3452

член аргумента списка не является константой

Аргумент передан в атрибут, ожидающий константу, значение которого можно вычислить во время компиляции.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3452:

```
// C3452.cpp
// compile with: /c
int i;
[module( name="mod", type=dll, custom={i} ) ];   // C3452
// try the following line instead
// [module( name="mod", type=dll, custom={"a"} ) ];
```