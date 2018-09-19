---
title: Ошибка компилятора C2798 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2798
dev_langs:
- C++
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88241989d54e1a068b226b59091a381f531dee9e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028861"
---
# <a name="compiler-error-c2798"></a>Ошибка компилятора C2798

«super::member» является неоднозначным

Несколько унаследованных структур содержат член, на который существует ссылка [super](../../cpp/super.md). Может исправить ошибку, либо:

- Удаление B1 и B2 из списка наследования г.

- Изменение имени члена данных в B1 и B2.

Следующий пример приводит к возникновению ошибки C2798:

```
// C2798.cpp
struct B1 {
   int i;
};

struct B2 {
   int i;
};

struct D : B1, B2 {
   void g() {
      __super::i = 4; // C2798
   }
};
```