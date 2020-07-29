---
title: Ошибка компилятора C2218
ms.date: 11/04/2016
f1_keywords:
- C2218
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
ms.openlocfilehash: 97f3290ef8bcb6a91442effdbf84261c03545ce2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87209530"
---
# <a name="compiler-error-c2218"></a>Ошибка компилятора C2218

> __vectorcall не может использоваться с /arch:IA32

**`__vectorcall`** Соглашение о вызовах поддерживается только в машинном коде на процессорах x86 и x64, включающих Streaming SIMD Extensions 2 (SSE2) и более поздних версий. Дополнительные сведения см. на веб-сайте [`__vectorcall`](../../cpp/vectorcall.md).

Чтобы устранить эту ошибку, измените параметры компилятора на целевые наборы инструкций SSE2, AVX или AVX2. Дополнительные сведения см. в разделе [ `/arch` (x86)](../../build/reference/arch-x86.md).
