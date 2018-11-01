---
title: Предупреждение компилятора (уровень 3) C4240
ms.date: 11/04/2016
f1_keywords:
- C4240
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
ms.openlocfilehash: fe5306cc7909138fea0159553b53c2adc6a46dc0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498245"
---
# <a name="compiler-warning-level-3-c4240"></a>Предупреждение компилятора (уровень 3) C4240

использовано нестандартное расширение: уровень доступа «имя_класса» теперь задан как «спецификатор доступа», ранее он был определен как «спецификатор доступа»

В режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), невозможно изменить параметры доступа к вложенным классом. При использовании расширений Майкрософт по умолчанию (/Ze) можно со следующим предупреждением.

## <a name="example"></a>Пример

```
// C4240.cpp
// compile with: /W3
class X
{
private:
   class N;
public:
   class N
   {   // C4240
   };
};

int main()
{
}
```