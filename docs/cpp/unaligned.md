---
title: __unaligned
ms.date: 12/17/2018
f1_keywords:
- __unaligned_cpp
- __unaligned
- _unaligned
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
ms.openlocfilehash: 8eb1b93aa55601125600b6c69d9bff3d9ca43aa3
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53626868"
---
# <a name="unaligned"></a>__unaligned

**Системам Microsoft**. При объявлении указателя с **__unaligned** модификатор, компилятор предполагает, что указатель обращается к данным, не выровнен. Следовательно соответствующих платформе код создается для обработки операций чтения невыровненных и записывает через указатель.

## <a name="remarks"></a>Примечания

Этот модификатор описывает выравнивание данных, указывает указатель; предполагается, что сам указатель быть выровнены.

Необходимость **__unaligned** ключевое слово зависит от платформы и среды. Неспособность соответствующим образом пометить данных может привести к сбоям оборудования и заканчивая снижения производительности. **__Unaligned** модификатор не является допустимым для x86 платформы.

Для совместимости с предыдущими версиями **_unaligned** является синонимом **__unaligned** Если параметр компилятора [/Za \(отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) указывается.

Дополнительные сведения о выравнивании см. в разделах:

- [align](../cpp/align-cpp.md)

- [Оператор __alignof](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (выравнивание члена структуры)](../build/reference/zp-struct-member-alignment.md)

- [Примеры выравнивания структуры](../build/x64-software-conventions.md#examples-of-structure-alignment)

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)