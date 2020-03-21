---
title: MACRO
ms.date: 12/16/2019
f1_keywords:
- MACRO
helpviewer_keywords:
- MACRO directive
ms.assetid: 89434f7c-bc2c-4e91-8940-fe2db8785233
ms.openlocfilehash: 8eb0afdf73270c3e741f43b2e1fba02fe965846c
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076139"
---
# <a name="macro"></a>MACRO

Помечает блок макроса *именем name* и устанавливает заполнители *параметров* для аргументов, передаваемых при вызове макроса.

## <a name="syntax"></a>Синтаксис

> *имя***макроса** ⟦*параметр* ⟦ **: req** | : =*default* | *args* **: VARARG**⟧... ⟧\
> *инструкции*\
⟦**Goto** :*макролабелид*⟧ \
> ⟦**Екситм**⟧ \
> **Ендм** ⟦*значение*⟧

## <a name="remarks"></a>Примечания

Функция-макрос возвращает *значение* в вызывающую инструкцию.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[GoTo (MASM)](goto-masm.md)\
[Ендм](endm.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
