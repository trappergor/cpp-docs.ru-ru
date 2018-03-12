---
title: "__unaligned | Документы Microsoft"
ms.custom: 
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a9f30e2b268be6f9398cf0af40d66b786c7cdca9
ms.sourcegitcommit: eb246547c7c9adc7d7ac4083ef09bf6e54dec914
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2018
---
# <a name="unaligned"></a>__unaligned

**К системам Microsoft**. При объявлении указателя с модификатором `__unaligned` компилятор предполагает, что указатель обращается к данным без выравнивания. Следовательно соответствующих платформе код создается для обработки невыровненных операций чтения и записывает через указатель.

## <a name="remarks"></a>Примечания

Этот модификатор описывает выравнивание данных, подразумевающие указателя; предполагается, что сам указатель быть выровнены.

Необходимость `__unaligned` ключевое слово различается в зависимости от платформы и среды. Не удалось пометить данные соответствующим образом можно приводят к проблемам, от снижения производительности до сбоям оборудования. `__unaligned` Модификатор не является допустимым для x86 платформы.

Дополнительные сведения о выравнивании см. в разделах:

- [align](../cpp/align-cpp.md)

- [Оператор __alignof](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (выравнивание члена структуры)](../build/reference/zp-struct-member-alignment.md)

- [Примеры выравнивания структуры](../build/examples-of-structure-alignment.md)

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)
