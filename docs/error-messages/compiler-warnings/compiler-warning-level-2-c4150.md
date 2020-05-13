---
title: Предупреждение компилятора (уровень 2) C4150
ms.date: 11/04/2016
f1_keywords:
- C4150
helpviewer_keywords:
- C4150
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
ms.openlocfilehash: c4d84165c7fcda4ceab94b1380a818236f6f5ea5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162118"
---
# <a name="compiler-warning-level-2-c4150"></a>Предупреждение компилятора (уровень 2) C4150

удаление указателя на неполный тип "тип"; деструктор не вызван

Оператор **Delete** вызывается для удаления типа, который был объявлен, но не определен, поэтому компилятору не удается найти деструктор.

Следующий пример приводит к возникновению ошибки C4150:

```cpp
// C4150.cpp
// compile with: /W2
class  IncClass;

void NoDestruct( IncClass* pIncClass )
{
   delete pIncClass;
} // C4150, define class to resolve

int main()
{
}
```
