---
title: Предупреждение командной строки D9043
ms.date: 11/04/2016
f1_keywords:
- D9043
helpviewer_keywords:
- D9043
ms.assetid: 9263e28d-217b-414c-bfb6-86efd3c27a77
ms.openlocfilehash: 62834c5f245bc1c0f6197638e4608b7fe71e7eb1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62213498"
---
# <a name="command-line-warning-d9043"></a>Предупреждение командной строки D9043

Недопустимое значение «порог_предупреждения» для параметра «параметр_компилятора»; при условии, что "4999"; Предупреждения анализа кода не связаны с уровнями предупреждений

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C9043.

```
// D9043.cpp
// compile with: /analyze /w16001
// D9043 warning expected
int main() {}
```