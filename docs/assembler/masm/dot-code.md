---
title: .CODE
ms.date: 12/06/2019
f1_keywords:
- .CODE
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
ms.openlocfilehash: 36d9c01d2a24b446ddc91fe73f3cb677067b3e4c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74987919"
---
# <a name="code-32-bit-masm"></a>. КОД (32-разрядный компилятор MASM)

При использовании с [. MODEL](../../assembler/masm/dot-model.md)указывает начало сегмента кода.

## <a name="syntax"></a>Синтаксис

> **. КОД** ⟦*имя*⟧

### <a name="parameters"></a>Параметры

*имя*\
Необязательный параметр, указывающий имя сегмента кода. Имя по умолчанию — **_TEXT** для мелких, небольших, сжатых и плоских [моделей](../../assembler/masm/dot-model.md). Имя по умолчанию — *modulename*_TEXT для других моделей.

## <a name="see-also"></a>См. также:

[Справочник по директивам](../../assembler/masm/directives-reference.md)\
[.DATA](../../assembler/masm/dot-data.md)
