---
title: Предупреждение средств компоновщика LNK4253 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4253
dev_langs:
- C++
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d26d688825f504cbce8224adc9a5766a555d2fc8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016823"
---
# <a name="linker-tools-warning-lnk4253"></a>Предупреждение средств компоновщика LNK4253

раздел «раздел 1», не объединены в раздел «2»; Слияние уже выполнено с «section3»

Компоновщик обнаружил несколько конфликтующих запросов объединения. Компоновщик будет игнорировать один из запросов.

Объект **/MERGE** параметр или директива и `from` раздел уже добавлены в другой раздел из-за предыдущего **/MERGE** параметре или директиве (или из-за явного объединения Компоновщик).

Чтобы устранить LNK4253, удалите один из запросов merge.

Если x x86 машин и Windows CE целевых объектов (ARM, MIPS, SH4 и Thumb) с Visual C++. Раздел CRT теперь только для чтения. Если код зависит от предыдущего поведения (. CRT имеют чтение и запись), мы опубликуем непредвиденное поведение.

Дополнительные сведения см. в следующих разделах:

- [/MERGE (слияние разделов)](../../build/reference/merge-combine-sections.md)

- [comment (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Пример

В следующем примере, компоновщик для слияния `.rdata` раздел дважды, но в разные разделы. Следующий пример приводит к возникновению ошибки LNK4253.

```
// LNK4253.cpp
// compile with: /W1 /link /merge:.rdata=text2
// LNK4253 expected
#pragma comment(linker, "/merge:.rdata=.text")
int main() {}
```