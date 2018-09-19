---
title: Предупреждение командной строки D9043 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9043
dev_langs:
- C++
helpviewer_keywords:
- D9043
ms.assetid: 9263e28d-217b-414c-bfb6-86efd3c27a77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d29371e147c693b2aa49f8dcf838841af3c75c8d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031877"
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