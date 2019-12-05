---
title: Предупреждение ML A4012
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A4012
helpviewer_keywords:
- A4012
ms.assetid: 842b1259-9679-4eeb-a02d-672a583a94e5
ms.openlocfilehash: 40aabc264c52a0b81fcd4e29d519433cf5fecdd6
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74854567"
---
# <a name="ml-warning-a4012"></a>Предупреждение ML A4012

**сведения о номере строки для сегмента без класса "CODE"**

В сегменте есть инструкции, не имеющие имени класса, которое заканчивается на "CODE". Ассемблер не создавал сведения информация CodeView для этих инструкций.

Информация CodeView не может обрабатывать модули с кодом в сегментах с именами классов, которые не заканчиваются на "CODE".

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>