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
ms.openlocfilehash: 1090a0f3345f749a2afbd80566a9af7b9ea32d53
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857259"
---
# <a name="__unaligned"></a>__unaligned

**Зависит от корпорации Майкрософт**. При объявлении указателя с модификатором **__unaligned** компилятор предполагает, что указатель обращается к несогласованным данным. Следовательно, код, соответствующий платформе, создается для управления несогласованными операциями чтения и записи через указатель.

## <a name="remarks"></a>Заметки

Этот модификатор описывает выравнивание данных, адресованных указателю; Предполагается, что указатель должен быть согласован.

Потребность в ключевом слове **__unaligned** зависит от платформы и среды. Неправильное пометка данных может привести к проблемам, от снижения производительности до сбоев оборудования. Модификатор **__unaligned** не является допустимым для платформы x86.

Для совместимости с предыдущими версиями **_unaligned** является синонимом для **__unaligned** , если только не указан параметр компилятора [/Za \(отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) .

Дополнительные сведения о выравнивании см. в разделах:

- [align](../cpp/align-cpp.md)

- [Оператор __alignof](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (выравнивание члена структуры)](../build/reference/zp-struct-member-alignment.md)

- [Примеры выравнивания структуры](../build/x64-software-conventions.md#examples-of-structure-alignment)

## <a name="see-also"></a>См. также:

[Ключевые слова](../cpp/keywords-cpp.md)