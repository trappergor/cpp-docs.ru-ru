---
title: .CODE
ms.date: 08/30/2018
f1_keywords:
- .CODE
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
ms.openlocfilehash: a5b6608ca71a2b406c54a06cd44ac2865211a8ac
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398581"
---
# <a name="code"></a>.CODE

При использовании с [. MODEL](../../assembler/masm/dot-model.md)указывает начало сегмента кода.

## <a name="syntax"></a>Синтаксис

> **. КОД** ⟦*имя*⟧

### <a name="parameters"></a>Параметры

*имя*\
Необязательный параметр, указывающий имя сегмента кода. Имя по умолчанию — **_TEXT** для мелких, небольших, сжатых и плоских [моделей](../../assembler/masm/dot-model.md). Имя по умолчанию — *modulename*_TEXT для других моделей.

## <a name="see-also"></a>См. также:

[Справочник по директивам](../../assembler/masm/directives-reference.md)\
[.DATA](../../assembler/masm/dot-data.md)
