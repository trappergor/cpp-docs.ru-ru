---
title: Предупреждение (уровень 3) C4159 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4159
dev_langs:
- C++
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43e3d63ad1d482222c4ffa7aa7435d0e660f3985
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223322"
---
# <a name="compiler-warning-level-3-c4159"></a>Компилятор предупреждение (уровень 3) C4159

> #<a name="pragma-pragmapop--has-popped-previously-pushed-identifier-identifier"></a>Директива pragma pragma(pop,...): извлечен ранее занесенный в стек идентификатор "*идентификатор*"

## <a name="remarks"></a>Примечания

Исходный код содержит **принудительной** инструкции с идентификатором для директивы pragma, за которым следует **pop** инструкции без идентификатора. В результате *идентификатор* открывшемся окне так что последующие использует из *идентификатор* может привести к непредвиденному поведению.

## <a name="example"></a>Пример

Чтобы устранить это предупреждение, добавьте идентификатор **pop** инструкции. Пример:

```cpp
// C4159.cpp
// compile with: /W3
#pragma pack(push, f)
#pragma pack(pop)   // C4159

// using the identifier resolves the warning
// #pragma pack(pop, f)

int main()
{
}
```