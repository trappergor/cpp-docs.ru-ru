---
title: Предупреждение компилятора (уровень 4) C4435 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c9a69e0d899e1a79c1d91b7c18c0eacaf66d32a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027301"
---
# <a name="compiler-warning-level-4-c4435"></a>Предупреждение компилятора (уровень 4) C4435

"class1": структура объекта в /vd2 изменится из-за виртуального базового класса "class2"

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

В стандартной компиляции параметр/vd1, производный класс не имеет `vtordisp` для указанного виртуального базового.  Если/vd2 или `#pragma vtordisp(2)` , `vtordisp` поле будет присутствовать, изменение макета объекта.  Это может привести к проблемам совместимость двоичных данных, если взаимодействующих модули обычно компилируются с разными `vtordisp` параметры.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4435.

```cpp
// C4435.cpp
// compile with: /c /W4
#pragma warning(default : 4435)
class A
{
public:
    virtual ~A() {}
};

class B : public virtual A  // C4435
{};
```

## <a name="see-also"></a>См. также

[vtordisp](../../preprocessor/vtordisp.md)<br/>
[/vd (отключение смещений при выполнении конструктора)](../../build/reference/vd-disable-construction-displacements.md)