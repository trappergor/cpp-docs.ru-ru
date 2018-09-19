---
title: __unaligned | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __unaligned_cpp
dev_langs:
- C++
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9593a0b3c6e6980f5be2ce9dcf13e505e94dcace
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040206"
---
# <a name="unaligned"></a>__unaligned

**Системам Microsoft**. При объявлении указателя с **__unaligned** модификатор, компилятор предполагает, что указатель обращается к данным, не выровнен. Следовательно соответствующих платформе код создается для обработки операций чтения невыровненных и записывает через указатель.

## <a name="remarks"></a>Примечания

Этот модификатор описывает выравнивание данных, указывает указатель; предполагается, что сам указатель быть выровнены.

Необходимость **__unaligned** ключевое слово зависит от платформы и среды. Неспособность соответствующим образом пометить данных может привести к сбоям оборудования и заканчивая снижения производительности. **__Unaligned** модификатор не является допустимым для x86 платформы.

Дополнительные сведения о выравнивании см. в разделах:

- [align](../cpp/align-cpp.md)

- [Оператор __alignof](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (выравнивание члена структуры)](../build/reference/zp-struct-member-alignment.md)

- [Примеры выравнивания структуры](../build/examples-of-structure-alignment.md)

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)