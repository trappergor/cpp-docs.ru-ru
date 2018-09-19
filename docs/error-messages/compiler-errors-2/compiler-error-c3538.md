---
title: Ошибка компилятора C3538 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3538
dev_langs:
- C++
helpviewer_keywords:
- C3538
ms.assetid: ef3698a5-7356-4c62-b9af-5d3a4baed958
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2034ebfcdf6a6d0ca37f649223f632fc1bbcd51
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043161"
---
# <a name="compiler-error-c3538"></a>Ошибка компилятора C3538

в списке объявлений спецификатор "auto" должен всегда выводить тот же самый тип

Все переменные в списке объявлений не были разрешены в один тип.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что все объявления `auto` в списке сопоставляются с одним типом.

## <a name="example"></a>Пример

Следующие выражения вызывают ошибку C3538. В каждом операторе объявляется несколько переменных, но каждое использование ключевого слова `auto` не разрешается в один тип.

```
// C3538.cpp
// Compile with /Zc:auto
// C3538 expected
int main()
{
// Variable x1 is a pointer to char, but y1 is a double.
   auto * x1 = "a", y1 = 3.14;
// Variable c is a char and c1 is char*, but c2, and c3 are pointers to pointers.
   auto c = 'a', *c1 = &c, * c2 = &c1, * c3 = &c2;
// Variable x2 is an int, but y2 is a double and z is a char.
   auto x2(1), y2(0.0), z = 'a';
// Variable a is a pointer to int, but b is a pointer to double.
   auto *a = new auto(1), *b = new auto(2.0);
   return 0;
}
```

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-keyword.md)