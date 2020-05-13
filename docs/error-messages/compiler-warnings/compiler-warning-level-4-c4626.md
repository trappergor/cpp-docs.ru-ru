---
title: Предупреждение компилятора (уровень 4) C4626
ms.date: 11/04/2016
f1_keywords:
- C4626
helpviewer_keywords:
- C4626
ms.assetid: 7f822ff4-a4a3-4f17-b45b-e8b7b4659a14
ms.openlocfilehash: 665a21d9f0221b2cf3db111142576669a3b5d728
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198268"
---
# <a name="compiler-warning-level-4-c4626"></a>Предупреждение компилятора (уровень 4) C4626

"производный класс": не удалось создать оператор присваивания, так как оператор присваивания для базового класса недоступен или удален

Оператор присваивания был удален или недоступен для базового класса, поэтому он не был создан для производного класса. Любая попытка назначить объекты этого типа приведет к ошибке компилятора.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

В следующем примере показано возникновение ошибки C4626 и приводятся сведения по ее устранению.

```
// C4626
// compile with: /W4
#pragma warning(default : 4626)
class B
{
// public:
   B& operator = (const B&)
   {
      return *this;
   }
};

class D : public B
{

}; // C4626 - to fix, make B's copy constructor public

int main()
{
   D m;
   D n;
   // m = n;   // this line will cause an error
}
```
