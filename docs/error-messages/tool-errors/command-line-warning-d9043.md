---
title: Предупреждение командной строки D9043
ms.date: 11/04/2016
f1_keywords:
- D9043
helpviewer_keywords:
- D9043
ms.assetid: 9263e28d-217b-414c-bfb6-86efd3c27a77
ms.openlocfilehash: 747f3cadd050b8f36c13fd28ae123f7a6dbdfb05
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74992094"
---
# <a name="command-line-warning-d9043"></a>Предупреждение командной строки D9043

Недопустимое значение "warning_level" для "compiler_option"; предполагается "4999"; Предупреждения анализа кода не связаны с уровнями предупреждений

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C9043.

```cpp
// D9043.cpp
// compile with: /analyze /w16001
// D9043 warning expected
int main() {}
```
