---
title: Ошибка компилятора C3488 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3488
dev_langs:
- C++
helpviewer_keywords:
- C3488
ms.assetid: 0a6fcd76-dd3b-48d7-abb3-22eccda96034
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15e1a21781eed96ee3a2a1430da8e43013393912
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061803"
---
# <a name="compiler-error-c3488"></a>Ошибка компилятора C3488

var не разрешен, если по умолчанию параметры передаются по ссылке

Если вы указываете, что для лямбда-выражения по умолчанию используется режим передачи по ссылке, то в предложение передачи этого выражения нельзя передать значение по ссылке.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Не передавайте переменную в предложение передачи явным образом.

- Не указывайте режим передачи по ссылке в качестве режима по умолчанию.

- Укажите режим передачи по значению в качестве режима по умолчанию.

- Передайте переменную в предложение передачи по значению. (Это может изменить поведение лямбда-выражения.)

## <a name="example"></a>Пример

В приведенном ниже примере возникает ошибка C3488, так как ссылка на переменную `n` появляется в предложении передачи лямбда-выражения, режим передачи по умолчанию которого — по ссылке.

```
// C3488a.cpp

int main()
{
   int n = 5;
   [&, &n]() { return n; } (); // C3488
}
```

## <a name="example"></a>Пример

В следующем примере показаны четыре возможных способа устранения ошибки C3488:

```
// C3488b.cpp

int main()
{
   int n = 5;

   // Possible resolution 1:
   // Do not explicitly pass &n to the capture clause.
   [&]() { return n; } ();

   // Possible resolution 2:
   // Do not specify by-reference as the default capture mode.
   [&n]() { return n; } ();

   // Possible resolution 3:
   // Specify by-value as the default capture mode.
   [=, &n]() { return n; } ();

   // Possible resolution 4:
   // Pass n by value to the capture clause.
   [n]() { return n; } ();
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)