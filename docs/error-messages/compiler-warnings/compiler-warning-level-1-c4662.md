---
title: Предупреждение компилятора (уровень 1) C4662
ms.date: 11/04/2016
f1_keywords:
- C4662
helpviewer_keywords:
- C4662
ms.assetid: 7efda273-d04a-47b7-ad65-ff1ff94b5ffc
ms.openlocfilehash: 4fdb57eecb17f4385c0c297c1a13902890e16fea
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175603"
---
# <a name="compiler-warning-level-1-c4662"></a>Предупреждение компилятора (уровень 1) C4662

явное создание экземпляра: для класса-шаблона "идентификатор1" нет определения, из которого можно взять специализацию "идентификатор2"

Указанный класс-шаблон был объявлен, но не определен.

## <a name="example"></a>Пример

```cpp
// C4662.cpp
// compile with: /W1 /LD
template<class T, int i> class MyClass; // no definition
template MyClass< int, 1>;              // C4662
```
