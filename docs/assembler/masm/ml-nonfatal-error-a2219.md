---
title: Некритичная ошибка ML A2219
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2219
helpviewer_keywords:
- A2219
ms.assetid: 5ebc2f40-e47e-4f8e-b7b9-960b9cfc9f6d
ms.openlocfilehash: cf2be5db2aa9c21597c199a6840f4aaa50e0a681
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74854593"
---
# <a name="ml-nonfatal-error-a2219"></a>Некритичная ошибка ML A2219

> Неправильное выравнивание для смещения в коде очистки

## <a name="remarks"></a>Заметки

Операнд для [&period;аллокстакк](../../assembler/masm/dot-allocstack.md) и [&period;саверег](../../assembler/masm/dot-savereg.md) должен быть кратен 8.  Операнд для [&period;SAVEXMM128](../../assembler/masm/dot-savexmm128.md) и [&period;сетфраме](../../assembler/masm/dot-setframe.md) должен быть кратен 16.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках машинного обучения](../../assembler/masm/ml-error-messages.md)
