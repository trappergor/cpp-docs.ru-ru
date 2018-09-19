---
title: Ошибка компилятора C2844 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2844
dev_langs:
- C++
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5dd4cbdc30523563207fe2a66c1c5cb158f84c94
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092107"
---
# <a name="compiler-error-c2844"></a>Ошибка компилятора C2844

«член»: не может быть членом интерфейса «интерфейс»

[Класс интерфейса](../../windows/interface-class-cpp-component-extensions.md) не может содержать элемент данных, если он также является свойством.

Ничего, кроме свойства или функции-члена не допускается в интерфейсе. Кроме того конструкторы, деструкторы и операторы не разрешены.

Следующий пример приводит к возникновению ошибки C2844:

```
// C2844a.cpp
// compile with: /clr /c
public interface class IFace {
   int i;   // C2844
   // try the following line instead
   // property int Size;
};
```
