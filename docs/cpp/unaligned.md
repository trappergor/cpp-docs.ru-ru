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
ms.openlocfilehash: 5f93aaa79fd7c3664ecf80d5007d5954002bce4a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160649"
---
# <a name="__unaligned"></a>__unaligned

**Зависит от корпорации Майкрософт**. При объявлении указателя с модификатором **__unaligned** компилятор предполагает, что указатель обращается к несогласованным данным. Следовательно, код, соответствующий платформе, создается для управления несогласованными операциями чтения и записи через указатель.

## <a name="remarks"></a>Remarks

Этот модификатор описывает выравнивание данных, адресованных указателю; Предполагается, что указатель должен быть согласован.

Потребность в ключевом слове **__unaligned** зависит от платформы и среды. Неправильное пометка данных может привести к проблемам, от снижения производительности до сбоев оборудования. Модификатор **__unaligned** не является допустимым для платформы x86.

Для совместимости с предыдущими версиями **_unaligned** является синонимом для **__unaligned** , если только не указан параметр компилятора [/Za \(отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) .

Дополнительные сведения о выравнивании см. в разделах:

- [align](../cpp/align-cpp.md)

- [Оператор __alignof](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (выравнивание члена структуры)](../build/reference/zp-struct-member-alignment.md)

- [Примеры выравнивания структуры](../build/x64-software-conventions.md#examples-of-structure-alignment)

## <a name="see-also"></a>См. также раздел

[Ключевые слова](../cpp/keywords-cpp.md)
