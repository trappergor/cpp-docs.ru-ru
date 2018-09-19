---
title: Предупреждение (уровень 1) C4042 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4042
dev_langs:
- C++
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bef2071cf31123b5b172df2651c0d6a6d87d4fc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067481"
---
# <a name="compiler-warning-level-1-c4042"></a>Компилятор предупреждение (уровень 1) C4042

«Идентификатор»: имеет недопустимый класс хранения

Заданный класс хранения не может использоваться со следующим идентификатором в данном контексте. Компилятор использует класс хранения по умолчанию вместо:

- `extern`, если *идентификатор* является функцией.

- **Автоматическое**, если *идентификатор* формального параметра или локальной переменной.

- Класс не хранения, если *идентификатор* является глобальной переменной.

Это предупреждение может быть вызвано задан класс хранения, отличные от **зарегистрировать** в объявлении параметра.

Следующий пример приводит к возникновению ошибки C4042

```
// C4042.cpp
// compile with: /W1 /LD
int func2( __declspec( thread ) int tls_i )    // C4042
// try the following line instead
// int func2( int tls_i )
{
   return tls_i;
}
```