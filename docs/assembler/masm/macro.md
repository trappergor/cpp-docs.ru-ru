---
title: MACRO
ms.date: 12/16/2019
f1_keywords:
- MACRO
helpviewer_keywords:
- MACRO directive
ms.assetid: 89434f7c-bc2c-4e91-8940-fe2db8785233
ms.openlocfilehash: 23c6b0aefae856da449da574669e8475122c7556
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75312954"
---
# <a name="macro"></a>MACRO

Помечает блок макроса *именем name* и устанавливает заполнители *параметров* для аргументов, передаваемых при вызове макроса.

## <a name="syntax"></a>Синтаксис

> *имя***макроса** ⟦*параметр* ⟦ **: req** | : =*default* | *args* **: VARARG**⟧... ⟧\
> *инструкции*\
⟦**Goto** :*макролабелид*⟧ \
> ⟦**Екситм**⟧ \
> **Ендм** ⟦*значение*⟧

## <a name="remarks"></a>Заметки

Функция-макрос возвращает *значение* в вызывающую инструкцию.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[GoTo (MASM)](goto-masm.md)\
[Ендм](endm.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)

