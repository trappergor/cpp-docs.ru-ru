---
title: Предупреждение компилятора (уровень 3) C4240
ms.date: 11/04/2016
f1_keywords:
- C4240
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
ms.openlocfilehash: 9e4d33bd0151e4355903c7d10b667ced405a2471
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161572"
---
# <a name="compiler-warning-level-3-c4240"></a>Предупреждение компилятора (уровень 3) C4240

использовано нестандартное расширение: доступ к "className" теперь определен как "спецификатор доступа", ранее он был определен как "спецификатор доступа"

В режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) нельзя изменить доступ к вложенному классу. В разделе расширения Майкрософт по умолчанию (/Ze) можно с помощью этого предупреждения.

## <a name="example"></a>Пример

```cpp
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
