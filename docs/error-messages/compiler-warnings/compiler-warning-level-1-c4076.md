---
title: Предупреждение компилятора (уровень 1) C4076 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4076
dev_langs:
- C++
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 928b0a78c09773e334c1a291877b74304dab66ec
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198482"
---
# <a name="compiler-warning-level-1-c4076"></a>Предупреждение компилятора (уровень 1) C4076

> "*модификатор типа*": не может использоваться с типом "*typename*"

## <a name="remarks"></a>Примечания

Модификатор типа, будь то **автоматический** или **без знака**, нельзя использовать с типом отличный от integer. *модификатор типа* учитывается.
  
## <a name="example"></a>Пример  

Следующий пример приводит к возникновению ошибки C4076; Чтобы устранить проблему, удалите **без знака** модификатор типа:

```cpp
// C4076.cpp  
// compile with: /W1 /LD  
unsigned double x;   // C4076  
```