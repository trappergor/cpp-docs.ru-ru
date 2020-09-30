---
title: Предупреждение компилятора (уровень 4) C4690
ms.date: 07/03/2018
f1_keywords:
- C4690
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
ms.openlocfilehash: de996128c68ebf96b4a00f6206cbaf54d97ca275
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509967"
---
# <a name="compiler-warning-level-4-c4690"></a>Предупреждение компилятора (уровень 4) C4690

> \[ emitidl (POP)]: больше точек присутствия, чем push-уведомления

## <a name="remarks"></a>Remarks

Атрибут [emitidl](../../windows/attributes/emitidl.md) был извлечен на один раз больше, чем занесен.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению предупреждения C4690: Чтобы устранить эту проблему, убедитесь, что атрибут извлекается в точном количестве раз, когда он был отправлен.

```cpp
// C4690.cpp
// compile with: /c /W4
[emitidl(pop)];   // C4690
class x {};
```
