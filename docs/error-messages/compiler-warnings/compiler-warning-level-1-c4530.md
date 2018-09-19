---
title: Предупреждение компилятора (уровень 1) C4530 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4530
dev_langs:
- C++
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbfbc67377dd48eeb692bdd4cac1f113fbdf7f6a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110462"
---
# <a name="compiler-warning-level-1-c4530"></a>Предупреждение компилятора (уровень 1) C4530

Обработчик исключений C++ используется, но семантика уничтожения объектов не включены. Задайте параметр/EHsc

Была использована обработка исключений C++, но [/EHsc](../../build/reference/eh-exception-handling-model.md) не был выбран.

Если параметр/EHsc не была включена, объект автоматически сохраняемый во фрейме между функцией throw и функцией, перехватывающей исключение, не будут уничтожены. Тем не менее, объект с автоматическим хранилищем создан в **попробуйте** или **catch** блок будут уничтожены.

Следующий пример приводит к возникновению ошибки C4530:

```
// C4530.cpp
// compile with: /W1
int main() {
   try{} catch(int*) {}   // C4530
}
```

Скомпилируйте образец с/EHsc, чтобы устранить это предупреждение.