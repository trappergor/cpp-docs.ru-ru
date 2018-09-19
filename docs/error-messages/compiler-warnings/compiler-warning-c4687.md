---
title: Предупреждение компилятора C4687 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4687
dev_langs:
- C++
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d813ce6d666431cfc3f74d1409012a4a0aec897
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118717"
---
# <a name="compiler-warning-c4687"></a>Предупреждение компилятора C4687

«класс»: Запечатанный абстрактный класс не может реализовывать интерфейс «интерфейс»

Запечатанный абстрактный тип обычно содержит только для хранения статических функций-членов.

Дополнительные сведения см. в разделе [абстрактный](../../windows/abstract-cpp-component-extensions.md)и [запечатанный](../../windows/sealed-cpp-component-extensions.md).

C4687 выдается как ошибка по умолчанию. Вы можете отключить C4687 с [предупреждение](../../preprocessor/warning.md) директивы pragma. Если вы уверены, что вы хотите реализовать интерфейс в Запечатанный абстрактный тип, можно отключить C4687.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4687.

```
// C4687.cpp
// compile with: /clr /c
interface class A {};

ref struct B sealed abstract : A {};   // C4687
ref struct C sealed : A {};   // OK
ref struct D abstract : A {};   // OK
```