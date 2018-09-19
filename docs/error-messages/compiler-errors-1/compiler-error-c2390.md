---
title: Ошибка компилятора C2390 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2390
dev_langs:
- C++
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5de5a9af8f8aa04219f0a7d61162336745fd4bfa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098218"
---
# <a name="compiler-error-c2390"></a>Ошибка компилятора C2390

«Идентификатор»: неправильный класс хранения «спецификатор»

Класс хранения не является допустимым для глобальной области идентификатора. Класс хранения по умолчанию используется вместо недопустимый класс.

Возможные решения:

- Если идентификатор является функцией, объявите его с `extern` хранилища.

- Если идентификатор является формальным параметром или локальной переменной, объявите его с хранилищем автоматически.

- Если идентификатор является глобальной переменной, объявите его без класса хранения (автоматическое хранилище).

## <a name="example"></a>Пример

- Следующий пример приводит к возникновению ошибки C2390:

```
// C2390.cpp
register int i;   // C2390

int main() {
   register int j;   // OK
}
```