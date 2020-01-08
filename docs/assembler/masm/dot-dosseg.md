---
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: e27b0ae185542c11ee29119575d5c8225501f71e
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75313851"
---
# <a name="dosseg-32-bit-masm"></a>. ДОССЕГ (32-разрядный компилятор MASM)

Упорядочивает сегменты в соответствии с соглашением о сегментах MS-DOS: сначала код, затем сегменты не в ДГРАУП, а затем сегменты в ДГРАУП. (только 32-разрядный MASM.)

## <a name="syntax"></a>Синтаксис

> **.DOSSEG**

## <a name="remarks"></a>Заметки

Сегменты в ДГРАУП следуют в следующем порядке: сегменты не в BSS или стек, затем сегменты BSS и, наконец, сегменты СТЕКа. В основном используется для обеспечения поддержки Информация CodeView в изолированных программах MASM. То же, что и [доссег](dosseg.md).

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
