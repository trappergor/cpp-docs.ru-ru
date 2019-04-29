---
title: Компилятор предупреждение (уровень 1) C4103
ms.date: 11/04/2016
f1_keywords:
- C4103
helpviewer_keywords:
- C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
ms.openlocfilehash: 15d7403d461467e33b7e89957821a311179d33a7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300292"
---
# <a name="compiler-warning-level-1-c4103"></a>Компилятор предупреждение (уровень 1) C4103

«имя_файла»: выравнивание изменилось после включения заголовка, возможно, из-за отсутствия #pragma pack(pop)

Упаковка влияет на структуру классов, и обычно, если упаковки изменений в файлах заголовков, могут возникнуть проблемы.

Используйте директиву #pragma [пакет](../../preprocessor/pack.md)(pop) перед выходом из файла заголовка, чтобы устранить это предупреждение.

Следующий пример приводит к возникновению ошибки C4103:

```
// C4103.h
#pragma pack(push, 4)

// defintions and declarations

// uncomment the following line to resolve
// #pragma pack(pop)
```

Затем:

```
// C4103.cpp
// compile with: /LD /W1
#include "c4103.h"   // C4103
```