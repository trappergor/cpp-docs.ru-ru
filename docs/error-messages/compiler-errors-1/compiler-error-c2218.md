---
title: Ошибка компилятора C2218
ms.date: 11/04/2016
f1_keywords:
- C2218
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
ms.openlocfilehash: db14c37992fc1e2dd409c653d622d3419fcae4f3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206652"
---
# <a name="compiler-error-c2218"></a>Ошибка компилятора C2218

__vectorcall не может использоваться с /arch:IA32

Соглашение о вызовах `__vectorcall` поддерживается только в машинном коде для процессоров x86 и x64, в которых используется набор инструкций SSE2 и выше. Дополнительные сведения см. в разделе [__vectorcall](../../cpp/vectorcall.md).

Чтобы устранить эту ошибку, измените параметры компилятора на целевые наборы инструкций SSE2, AVX или AVX2. Дополнительные сведения см. в разделе [/arch (x86)](../../build/reference/arch-x86.md).
