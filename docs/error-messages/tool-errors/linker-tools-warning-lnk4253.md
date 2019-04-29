---
title: Предупреждение средств компоновщика LNK4253
ms.date: 11/04/2016
f1_keywords:
- LNK4253
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
ms.openlocfilehash: d2fd7238a3f57b11b91813bd40b66cb3e9f47202
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352530"
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