---
title: Предупреждение компилятора (уровень 4) C4435
ms.date: 11/04/2016
f1_keywords:
- C4435
helpviewer_keywords:
- C4435
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
ms.openlocfilehash: 8021b6e4650a03b16c96711b8afe4f5fa57d2f07
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185351"
---
# <a name="compiler-warning-level-4-c4435"></a>Предупреждение компилятора (уровень 4) C4435

"class1": структура объекта в /vd2 изменится из-за виртуального базового класса "class2"

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

В параметре компиляции по умолчанию/vd1 производный класс не имеет поля `vtordisp` для указанной виртуальной базы.  Если действует/vd2 или `#pragma vtordisp(2)`, будет указано `vtordisp` поле, в котором изменяется макет объекта.  Это может привести к проблемам совместимости с двоичными данными при компиляции взаимодействующих модулей с разными параметрами `vtordisp`.

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

## <a name="see-also"></a>См. также раздел

[vtordisp](../../preprocessor/vtordisp.md)<br/>
[/vd (отключение смещений при выполнении конструктора)](../../build/reference/vd-disable-construction-displacements.md)
