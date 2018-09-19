---
title: Предупреждение компилятора (уровень 1) C4377 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4377
dev_langs:
- C++
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 613ebe183b61c6b9894ed3b726f90061e2b24ef6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047178"
---
# <a name="compiler-warning-level-1-c4377"></a>Предупреждение компилятора (уровень 1) C4377

собственные типы являются закрытыми по умолчанию; -d1PrivateNativeTypes запрещен

В предыдущих выпусках собственные типы в сборках были открытыми по умолчанию и параметр компилятора внутренней, недокументированной (**/d1PrivateNativeTypes**) был использован для их преобразования в закрытый.

Все типы в собственном и CLR, теперь по умолчанию являются частными в сборке, поэтому **/d1PrivateNativeTypes** больше не используется.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4377.

```
// C4377.cpp
// compile with: /clr /d1PrivateNativeTypes /W1
// C4377 warning expected
int main() {}
```