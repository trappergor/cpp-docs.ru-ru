---
title: .STACK
ms.date: 11/05/2019
f1_keywords:
- .STACK
helpviewer_keywords:
- .STACK directive
ms.assetid: 70019463-5d4f-41b6-8464-023a8ac2466f
ms.openlocfilehash: 78c089c771e8e5a8c82905578ec2377246a44a0e
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703532"
---
# <a name="stack-32-bit-masm"></a>. СТЕК (32-разрядный MASM)

При использовании с [. MODEL](../../assembler/masm/dot-model.md)определяет сегмент стека (с стеком имен сегментов). Необязательный `size` указывает число байтов для стека (по умолчанию 1 024). Директива `.STACK` автоматически закрывает оператор Stack. (только 32-разрядный MASM.)

## <a name="syntax"></a>Синтаксис

> . STACK [[размер]]

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>