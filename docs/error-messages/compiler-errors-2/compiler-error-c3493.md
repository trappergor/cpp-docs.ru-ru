---
title: Ошибка компилятора C3493 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3493
dev_langs:
- C++
helpviewer_keywords:
- C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad3c46117e77d432af27321165f1e1ab93d2ef3c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045111"
---
# <a name="compiler-error-c3493"></a>Ошибка компилятора C3493

"переменная" нельзя передать неявно, поскольку не задан режим передачи по умолчанию

Предложение пустой передачи лямбда-выражения ( `[]`) указывает на то, что лямбда-выражение не передает никаких переменных явно или неявно.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Укажите режим передачи по умолчанию или

- явно передайте одну или несколько переменных.

## <a name="example"></a>Пример

В приведенном ниже примере возникает ошибка C3493, так как в нем изменяется внешняя переменная, но указывается предложение пустой передачи.

```
// C3493a.cpp

int main()
{
   int m = 55;
   [](int n) { m = n; }(99); // C3493
}
```

## <a name="example"></a>Пример

В приведенном ниже примере ошибка C3493 устраняется путем указания передачи по ссылке в качестве режима передачи по умолчанию.

```
// C3493b.cpp

int main()
{
   int m = 55;
   [&](int n) { m = n; }(99);
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)