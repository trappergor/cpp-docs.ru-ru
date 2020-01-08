---
title: LOCAL (MASM)
ms.date: 12/16/2019
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: 2bef6b26f1b922be6512bd6ebe8e0b2627e86f45
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317153"
---
# <a name="local"></a>LOCAL

В первой директиве в макросе **Local** определяет метки, уникальные для каждого экземпляра макроса.

## <a name="syntax"></a>Синтаксис

> **Локальный** *LocalId* ⟦, *LocalId* ... ⟧
>
> **Local** *лабелид* ⟦ __\[__ *число* __]__ ⟧ ⟦ __:__ *куалифиедтипе*⟧ ⟦ __,__ *лабелид* ⟦ __\[__ *Count* __]__ ⟧ ⟦*куалифиедтипе*⟧... ⟧

## <a name="remarks"></a>Заметки

Во второй директиве в определении процедуры (**proc**) **Local** создает переменные на основе стека, которые существуют в течение данной процедуры. *Лабелид* может быть простой переменной или массивом, содержащим элементы *Count* , где *Count* является константным выражением.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
