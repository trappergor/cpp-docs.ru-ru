---
title: .CODE
ms.date: 12/17/2019
f1_keywords:
- .CODE
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
ms.openlocfilehash: 0975e96e670400b7fa221ae2d1b9982b5cee613b
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75314150"
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

