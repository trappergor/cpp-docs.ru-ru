---
title: Предупреждение компилятора (уровень 1) C4103
ms.date: 11/04/2016
f1_keywords:
- C4103
helpviewer_keywords:
- C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
ms.openlocfilehash: 456e7d393eb751e99c1969619ccfdcc649193c75
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627056"
---
# <a name="compiler-warning-level-1-c4103"></a>Предупреждение компилятора (уровень 1) C4103

"имяфайла": выравнивание изменено после включения заголовка, возможно, из-за отсутствующего пакета #pragma (POP)

Упаковка влияет на макет классов, и обычно при изменении упаковки в файлах заголовков могут возникнуть проблемы.

Чтобы устранить это предупреждение, используйте [пакет](../../preprocessor/pack.md)#pragma (POP) перед выходом из файла заголовка.

Следующий пример приводит к возникновению ошибки C4103:

```cpp
// C4103.h
#pragma pack(push, 4)

// defintions and declarations

// uncomment the following line to resolve
// #pragma pack(pop)
```

Затем:

```cpp
// C4103.cpp
// compile with: /LD /W1
#include "c4103.h"   // C4103
```