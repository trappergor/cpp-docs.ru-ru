---
title: Предупреждение средств компоновщика LNK4254
ms.date: 11/04/2016
f1_keywords:
- LNK4254
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
ms.openlocfilehash: 8431bd2d89fd5df5cf076ad006ab04006f552c4c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988059"
---
# <a name="linker-tools-warning-lnk4254"></a>Предупреждение средств компоновщика LNK4254

раздел "Section1" (offset) объединен в "section2" (offset) с различными атрибутами

Содержимое одного раздела было объединено в другой, но атрибуты двух разделов различаются. Программа может дать непредвиденные результаты. Например, данные, которые должны быть доступны только для чтения, теперь могут находиться в разделе, доступном для записи.

Чтобы разрешить LNK4254, измените или удалите запрос на слияние.

При нацеливании на компьютеры x86 и Windows CE (ARM, MIPS, SH4 и Thumb) с помощью C++визуального элемента. Раздел CRT доступен только для чтения. Если код зависит от предыдущего поведения (. Разделы CRT доступны для чтения и записи. это может привести к непредвиденному поведению.

Дополнительные сведения см. в следующих разделах:

- [/MERGE (слияние разделов)](../../build/reference/merge-combine-sections.md)

- [comment (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки LNK4254.

```cpp
// LNK4254.cpp
// compile with: /W1 /link /WX
// LNK4254 expected
#pragma comment(linker, "/merge:.data=.text")
int main() {}
```
