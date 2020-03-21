---
title: .CODE
ms.date: 12/17/2019
f1_keywords:
- .CODE
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
ms.openlocfilehash: 7e53befcc46319d0ecf2287ab96a19a73a0b0b85
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076278"
---
# <a name="code"></a>.CODE

(только 32-разрядный MASM.) При использовании с [. MODEL](dot-model.md)указывает начало сегмента кода.

## <a name="syntax"></a>Синтаксис

> **. КОД** ⟦*имя*⟧ \
> ⟦ *сегментитем* ⟧... \
> ⟦ *кодесегментнамеид* **заканчивается**;; ⟧\

### <a name="parameters"></a>Параметры

*имя*\
Необязательный параметр, указывающий имя сегмента кода. Имя по умолчанию — **_TEXT** для мелких, небольших, сжатых и плоских [моделей](dot-model.md). Имя по умолчанию — *modulename*_TEXT для других моделей.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[.\ данных](dot-data.md)
[Грамматика MASM BNF](masm-bnf-grammar.md)
