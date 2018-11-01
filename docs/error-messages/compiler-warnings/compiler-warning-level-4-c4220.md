---
title: Предупреждение компилятора (уровень 4) C4220
ms.date: 11/04/2016
f1_keywords:
- C4220
helpviewer_keywords:
- C4220
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
ms.openlocfilehash: 177fb01ba4181f72740724d107fe08e6680ed492
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542445"
---
# <a name="compiler-warning-level-4-c4220"></a>Предупреждение компилятора (уровень 4) C4220

varargs соответствует оставшимся параметрам

При использовании расширений Майкрософт по умолчанию (/Ze) указатель на функцию соответствует указатель на функцию с аналогичными, но переменными, аргументы.

## <a name="example"></a>Пример

```
// C4220.c
// compile with: /W4

int ( *pFunc1) ( int a, ... );
int ( *pFunc2) ( int a, int b);

int main()
{
   if ( pFunc1 != pFunc2 ) {};  // C4220
}
```

Такие указатели не совпадают в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).