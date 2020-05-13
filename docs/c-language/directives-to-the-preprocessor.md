---
title: Директивы препроцессору
ms.date: 11/04/2016
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
ms.openlocfilehash: 520d181c3a58ee2c626678a3afd9126f1ef183cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62234144"
---
# <a name="directives-to-the-preprocessor"></a>Директивы препроцессору

Директива указывает препроцессору C выполнять определенное действие в тексте программы перед компиляцией. [Директивы препроцессора](../preprocessor/preprocessor-directives.md) полностью описаны в *справочнике по препроцессору*. В следующем примере используется директива препроцессора `#define`.

```
#define MAX 100
```

Этот оператор указывает компилятору заменять каждое вхождение `MAX` на `100` перед компиляцией. Ниже перечислены директивы препроцессора компилятора C.

|#define|#endif|#ifdef|#line|
|--------------|-------------|-------------|------------|
|`#elif`|`#error`|**#ifndef**|**#pragma**|
|`#else`|`#if`|`#include`|`#undef`|

## <a name="see-also"></a>См. также

[Файлы с исходным кодом и исходные программы](../c-language/source-files-and-source-programs.md)
