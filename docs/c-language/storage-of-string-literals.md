---
title: Хранение строковых литералов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- string literals, storage
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 111acab00783de67dcb3ecc8b9d45fe112332158
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019528"
---
# <a name="storage-of-string-literals"></a>Хранение строковых литералов

Символы строкового литерала хранятся по порядку в смежных адресах памяти. Любая escape-последовательность (например, **\\\\** или **\\"**) внутри строкового литерала считается одним символом. В каждый строковый литерал автоматически добавляется нуль-символ (представленный escape-последовательностью **\0**), который обозначает его конец. (Это происходит на [этапе преобразования](../preprocessor/phases-of-translation.md) 7.) Обратите внимание, что компилятор не может сохранить две одинаковые строки отдельно с разными адресами. Ключ [/GF](../build/reference/gf-eliminate-duplicate-strings.md) указывает, что компилятор должен сохранять в исполняемом файле только одну копию одинаковых строк.

## <a name="remarks"></a>Примечания

**Блок, относящийся только к системам Microsoft**

Строки имеют статическую длительность хранения. Дополнительные сведения о длительности хранения см. в разделе [Классы хранения в C](../c-language/c-storage-classes.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Строковые литералы в C](../c-language/c-string-literals.md)