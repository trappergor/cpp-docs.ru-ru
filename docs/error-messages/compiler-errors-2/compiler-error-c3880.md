---
title: Ошибка компилятора C3880 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3880
dev_langs:
- C++
helpviewer_keywords:
- C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03cd1c953e4f0183fe71dcbcf4cc3bfb242b4f1c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074361"
---
# <a name="compiler-error-c3880"></a>Ошибка компилятора C3880

«var»: не может быть данными-членом литерала

Тип [литерала](../../windows/literal-cpp-component-extensions.md) должен быть атрибут, или во время компиляции можно преобразовать в один из следующих типов:

- целочисленный тип

- string

- Перечисление с целым или базовым типом

Следующий пример приводит к возникновению ошибки C3880:

```
// C3880.cpp
// compile with: /clr /c
ref struct Y1 {
   literal System::Decimal staticConst1 = 10;   // C3880
   literal int staticConst2 = 10;   // OK
};
```