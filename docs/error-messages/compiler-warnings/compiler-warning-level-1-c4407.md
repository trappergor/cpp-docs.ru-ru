---
title: Предупреждение компилятора (уровень 1) C4407 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4407
dev_langs:
- C++
helpviewer_keywords:
- C4407
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9a665dbb71157b37f72d3d0721357d00dc37230
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032608"
---
# <a name="compiler-warning-level-1-c4407"></a>Предупреждение компилятора (уровень 1) C4407

приведение между разных представлениями указателя на член, компилятор может создать неправильный код

Обнаружено неверное приведение.

Предупреждение C4407 может возникать из-за изменений работы компилятора в Visual C++ 2005. Указатель на член теперь требуется полное имя и оператор взятия адреса (&).

C4407 может возникать, если приведение между несколькими наследования указателя на член для одиночного наследования указателя на член. Иногда это может сработать, но иногда это невозможно, так как представление указателя на член одиночное наследование не содержит достаточно сведений. Компиляция с **/VMM** может помочь (Дополнительные сведения см. в разделе [/VMM, / vms и/vmv (представление общего назначения)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)). Можно также попробовать реорганизовать базовые классы; компилятор обнаруживает к потере данных при преобразовании, так как базовый класс с ненулевой смещением от производного.

Следующий пример приводит к возникновению ошибки C4407:

```
// C4407.cpp
// compile with: /W1 /c
struct C1 {};
struct C2 {};
struct C3 : C1, C2 {};

typedef void(C3::*PMF_C3)();
typedef void(C2::*PMF_C2)();

PMF_C2 f1(PMF_C3 pmf) {
   return (PMF_C2)pmf;   // C4407, change type of cast,
   // or reverse base class inheritance of C3 (i.e. : C2, C1)
}
```