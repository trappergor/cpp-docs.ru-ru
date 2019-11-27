---
title: GOTO (MASM)
ms.date: 08/30/2018
f1_keywords:
- goto
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: 424ff295fe37e7c5ff02897a01b99a7c75876f85
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397480"
---
# <a name="goto-masm"></a>GOTO (MASM)

Передает сборку в строку, помеченную **:** _макролабел_.

## <a name="syntax"></a>Синтаксис

> **Goto** *макролабел*

## <a name="remarks"></a>Примечания

**Оператор goto** разрешен только внутри [макросов](macro.md), [для](for-masm.md), [Форк](forc.md), [Repeat](repeat.md)и [while](while-masm.md) . Целевой объект *макролабел* должен быть единственной директивой в строке и должен предшествовать начальному двоеточию.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)
