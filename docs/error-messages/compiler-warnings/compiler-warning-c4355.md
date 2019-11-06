---
title: Предупреждение компилятора C4355
ms.date: 11/04/2016
f1_keywords:
- C4355
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
ms.openlocfilehash: f1f5e5be2606a03ec5e9ecd0c571f94c25f82494
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623751"
---
# <a name="compiler-warning-c4355"></a>Предупреждение компилятора C4355

'this': используется в основном списке инициализации членов

**Этот** указатель является допустимым только в нестатических функциях-членах. Его нельзя использовать в списке инициализаторов для базового класса.

Конструкторы базового класса и конструкторы членов класса вызываются перед **этим** конструктором. Фактически вы передали указатель на несконструированный объект другому конструктору. Если другие конструкторы обращаются к членам или вызывают функции членов для этого, результат будет неопределенным. Не следует использовать **этот** указатель, пока не завершится вся конструкция.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Следующий пример приводит к возникновению ошибки C4355:

```cpp
// C4355.cpp
// compile with: /w14355 /c
#include <tchar.h>

class CDerived;
class CBase {
public:
   CBase(CDerived *derived): m_pDerived(derived) {};
   ~CBase();
   virtual void function() = 0;

   CDerived * m_pDerived;
};

class CDerived : public CBase {
public:
   CDerived() : CBase(this) {};   // C4355 "this" used in derived c'tor
   virtual void function() {};
};

CBase::~CBase() {
   m_pDerived -> function();
}

int main() {
   CDerived myDerived;
}
```