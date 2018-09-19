---
title: Ошибка компилятора C2530 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2530
dev_langs:
- C++
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f41f9ec64e2074ed5e0cd2654f2b6bfec886bc07
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103199"
---
# <a name="compiler-error-c2530"></a>Ошибка компилятора C2530

«Идентификатор»: ссылки должны быть инициализированы

Необходимо инициализировать ссылку при ее объявлении, если она уже не объявлена:

- С помощью ключевого слова [extern](../../cpp/using-extern-to-specify-linkage.md).

- Как член класса, структуры или объединения (и он инициализируется в конструкторе).

- Как параметр в определении или объявлении функции.

- Как возвращаемый тип функции.

Следующий пример приводит к возникновению ошибки C2530:

```
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```