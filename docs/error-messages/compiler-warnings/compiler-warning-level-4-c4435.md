---
title: Предупреждение компилятора (уровень 4) C4435
ms.date: 11/04/2016
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
ms.openlocfilehash: 7db1d483f571289c5b890c223ba1e59ba3d1f41e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572332"
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