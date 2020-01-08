---
title: GOTO (MASM)
ms.date: 12/16/2019
f1_keywords:
- goto
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: f198658f9a4b85e0b5ec9b7a0c122241e57286f6
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317283"
---
# <a name="goto"></a>GOTO

Передает сборку в строку, помеченную **:** _макролабел_.

## <a name="syntax"></a>Синтаксис

> **Goto** *макролабел*

## <a name="remarks"></a>Заметки

**Оператор goto** разрешен только внутри [макросов](macro.md), [для](for-masm.md), [Форк](forc.md), [Repeat](repeat.md)и [while](while-masm.md) . Целевой объект *макролабел* должен быть единственной директивой в строке и должен предшествовать начальному двоеточию.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
