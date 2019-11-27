---
title: Предупреждение компилятора (уровень 4) C4032
ms.date: 11/04/2016
f1_keywords:
- C4032
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
ms.openlocfilehash: 52e80340a5157e9350b6d4bbf3bcabea0487e089
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541247"
---
# <a name="compiler-warning-level-4-c4032"></a>Предупреждение компилятора (уровень 4) C4032

формальный параметр "число" имеет другой тип при повышении уровня

Тип параметра несовместим с использованием специальных предложений по умолчанию с типом в предыдущем объявлении.

Это ошибка в ANSI C ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) и предупреждение в разделе расширения Майкрософт (/Ze).

## <a name="example"></a>Пример

```c
// C4032.c
// compile with: /W4
void func();
void func(char);   // C4032, char promotes to int

int main()
{
}
```