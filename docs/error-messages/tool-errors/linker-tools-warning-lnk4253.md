---
title: Предупреждение средств компоновщика LNK4253
ms.date: 11/04/2016
f1_keywords:
- LNK4253
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
ms.openlocfilehash: c3f45880571e5c06f76d5f063ff993e2f6b2be9b
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988088"
---
# <a name="linker-tools-warning-lnk4253"></a>Предупреждение средств компоновщика LNK4253

раздел "Section1" не объединен в "section2"; уже объединено с "section3"

Компоновщик обнаружил несколько конфликтующих запросов слияния. Компоновщик будет игнорировать один из запросов.

Обнаружен параметр или директива **/Merge** , и `from` раздел уже был объединен в другой раздел из-за предыдущего параметра **/Merge** или директивы (или из-за неявного слияния из компоновщика).

Чтобы разрешить LNK4253, удалите один из запросов слияния.

При нацеливании на компьютеры x86 и Windows CE (ARM, MIPS, SH4 и Thumb) с помощью C++визуального элемента. Теперь раздел CRT доступен только для чтения. Если код зависит от предыдущего поведения (. Разделы CRT доступны для чтения и записи. это может привести к непредвиденному поведению.

Дополнительные сведения см. в следующих разделах:

- [/MERGE (слияние разделов)](../../build/reference/merge-combine-sections.md)

- [comment (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Пример

В следующем примере компоновщику дается инструкция объединить `.rdata` раздел дважды, но в разные разделы. Следующий пример приводит к возникновению ошибки LNK4253.

```cpp
// LNK4253.cpp
// compile with: /W1 /link /merge:.rdata=text2
// LNK4253 expected
#pragma comment(linker, "/merge:.rdata=.text")
int main() {}
```
