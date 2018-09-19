---
title: Ошибка компилятора C2218 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2218
dev_langs:
- C++
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52c449381c6e8a7391706ed6097bc38576bc69fe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041289"
---
# <a name="compiler-error-c2218"></a>Ошибка компилятора C2218

__vectorcall не может использоваться с /arch:IA32

Соглашение о вызовах `__vectorcall` поддерживается только в машинном коде для процессоров x86 и x64, в которых используется набор инструкций SSE2 и выше. Дополнительные сведения см. в разделе [__vectorcall](../../cpp/vectorcall.md).

Чтобы устранить эту ошибку, измените параметры компилятора на целевые наборы инструкций SSE2, AVX или AVX2. Дополнительные сведения см. в разделе [/arch (x86)](../../build/reference/arch-x86.md).