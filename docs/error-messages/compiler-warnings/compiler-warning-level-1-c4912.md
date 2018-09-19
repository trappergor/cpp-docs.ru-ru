---
title: Предупреждение компилятора (уровень 1) C4912 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4912
dev_langs:
- C++
helpviewer_keywords:
- C4912
ms.assetid: ba1f1a66-8c20-4792-9ac8-43e49f729ae2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c80e7d3a6f9e3f97b05e1ec9e966de7f6d8a388d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047113"
---
# <a name="compiler-warning-level-1-c4912"></a>Предупреждение компилятора (уровень 1) C4912

"атрибут": поведение атрибута во вложенных UDT не определено

Атрибуты, применяемые ко вложенным UDT (определяемым пользователем типам, которые могут быть typedef, union или struct), могут игнорироваться.

В следующем коде показано, как это предупреждение может быть создано:

```
// C4912.cpp
// compile with: /W1
#include <windows.h>
[emitidl, module(name="xx")];

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface IMy
{
};

[coclass, default(IMy), appobject, uuid("00000000-0000-0000-0000-000000000001")]
class CMy : public IMy
{
   [export, v1_enum] typedef enum myEnum { k3_1 = 1, k3_2 = 2 } myEnumv;   // C4912
};
int main()
{
}
```