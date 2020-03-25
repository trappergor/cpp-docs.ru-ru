---
title: Предупреждение компилятора (уровень 1) C4661
ms.date: 11/04/2016
f1_keywords:
- C4661
helpviewer_keywords:
- C4661
ms.assetid: 603bb8b7-356d-4eef-924b-64d769bac5bd
ms.openlocfilehash: 43a3287787f831db23423412a9baf959929adfae
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199465"
---
# <a name="compiler-warning-level-1-c4661"></a>Предупреждение компилятора (уровень 1) C4661

"идентификатор": не указано подходящее определение для запроса явного создания экземпляра шаблона

Член класса шаблона не определен.

## <a name="example"></a>Пример

```cpp
// C4661.cpp
// compile with: /W1 /LD
template<class T> class MyClass {
public:
   void i();   // declaration but not definition
};
template MyClass< int >;  // C4661
```
