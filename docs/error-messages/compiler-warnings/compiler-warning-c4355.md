---
title: Предупреждение компилятора C4355
ms.date: 11/04/2016
f1_keywords:
- C4355
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
ms.openlocfilehash: ddc0d1968ae373ff1e81c98a513e6f84fdb885e1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165331"
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
