---
title: INVOKE
ms.date: 11/05/2019
f1_keywords:
- Invoke
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
ms.openlocfilehash: 853bc9cd22d866357a4cd2d695beccc3efc20acf
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703965"
---
# <a name="invoke-32-bit-masm"></a>INVOKE (32-разрядный MASM)

Вызывает процедуру по адресу, заданному *выражением*, передавая аргументы в стеке или в регистрах в соответствии со стандартными соглашениями о вызовах типа языка. (только 32-разрядный MASM.)

## <a name="syntax"></a>Синтаксис

> INVOKE, *выражение* [[, *аргументы*]]

## <a name="remarks"></a>Заметки

Каждый аргумент, передаваемый в процедуру, может быть выражением, парой регистров или выражением адреса (выражением предшествует `ADDR`).

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>