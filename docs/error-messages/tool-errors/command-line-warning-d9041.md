---
title: Предупреждение командной строки D9041 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9041
dev_langs:
- C++
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70bf82cfdca787898a02fb52926981bfd1a1b3e4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033385"
---
# <a name="command-line-warning-d9041"></a>Предупреждение командной строки D9041

Недопустимое значение «value» для «/ параметр»; при условии, что «value»; Добавьте «/ analyze» в параметры командной строки, при указании этого предупреждения

Номер предупреждения анализа кода был добавлен к **/wd**, **/we**, **/WO**, или **/wl** параметр командной строки без указания **/ analyze** параметр командной строки. Чтобы исправить эту ошибку, либо добавьте **/ analyze** параметр командной строки, или удалите недопустимый номер предупреждения из соответствующих **/w** параметр командной строки.

## <a name="example"></a>Пример

В следующем примере командной строки приводит к появлению предупреждения D9041:

```
cl /EHsc /LD /wd6001 filename.cpp
```

Чтобы устранить это предупреждение, добавьте **/ analyze** параметр командной строки. Если **/ analyze** — не поддерживается версией компилятора, удалите недопустимый номер предупреждения из **/wd** параметр.

## <a name="see-also"></a>См. также

[Ошибки командной строки с D8000 по D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[Параметры компилятора](../../build/reference/compiler-options.md)