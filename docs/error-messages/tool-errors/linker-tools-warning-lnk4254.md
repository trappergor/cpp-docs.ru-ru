---
title: Предупреждение средств компоновщика LNK4254 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4254
dev_langs:
- C++
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2ef421cbfa87ecab8a27dfa796eaa4eaacf7b70
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064651"
---
# <a name="linker-tools-warning-lnk4254"></a>Предупреждение средств компоновщика LNK4254

раздел «раздел 1» (смещение) объединены в раздел «2» (смещение) с разными атрибутами

Содержимое одного раздела было выполнено слияние в другой, но отличаются атрибуты из двух разделов. Программа может привести к непредвиденным результатам. Например данные, которые вы хотите прочитать только теперь возможно раздел, доступный для записи.

Чтобы устранить LNK4254, изменить или удалить запрос на слияние.

Если x x86 машин и Windows CE целевых объектов (ARM, MIPS, SH4 и Thumb) с Visual C++. CRT доступен только для чтения. Если код зависит от предыдущего поведения (. CRT имеют чтение и запись), мы опубликуем непредвиденное поведение.

Дополнительные сведения см. в следующих разделах:

- [/MERGE (слияние разделов)](../../build/reference/merge-combine-sections.md)

- [comment (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки LNK4254.

```
// LNK4254.cpp
// compile with: /W1 /link /WX
// LNK4254 expected
#pragma comment(linker, "/merge:.data=.text")
int main() {}
```