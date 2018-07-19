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
ms.openlocfilehash: 9d87998f7e9d579c012f5db2f38f20886c1e74c6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387038"
---
# <a name="storage-of-string-literals"></a>Хранение строковых литералов
Символы строкового литерала хранятся по порядку в смежных адресах памяти. Любая escape-последовательность (например, **\\\\** или **\\"**) внутри строкового литерала считается одним символом. В каждый строковый литерал автоматически добавляется нуль-символ (представленный escape-последовательностью **\0**), который обозначает его конец. (Это происходит на [этапе преобразования](../preprocessor/phases-of-translation.md) 7.) Обратите внимание, что компилятор не может сохранить две одинаковые строки отдельно с разными адресами. Ключ [/GF](../build/reference/gf-eliminate-duplicate-strings.md) указывает, что компилятор должен сохранять в исполняемом файле только одну копию одинаковых строк.  
  
## <a name="remarks"></a>Примечания  
 **Блок, относящийся только к системам Microsoft**  
  
 Строки имеют статическую длительность хранения. Дополнительные сведения о длительности хранения см. в разделе [Классы хранения в C](../c-language/c-storage-classes.md).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Строковые литералы в C](../c-language/c-string-literals.md)