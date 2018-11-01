---
title: Разряды
ms.date: 11/04/2016
helpviewer_keywords:
- bitfields
ms.assetid: e9a1010d-1e1b-487f-9943-3c574e08f544
ms.openlocfilehash: 3ff0092bbd31b8b1cd98fa56fb802c7ce28cb472
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652833"
---
# <a name="bitfields"></a>Разряды

Структура битовых полей ограничен 64 бита и может иметь тип автоматический int, int без знака, int64 или int64 без знака. Битовые поля, которые пересекают границу типа будет пропускать биты, чтобы выровнять битовое поле, чтобы далее выравнивание типа. Например целое число битовые поля не может пересекаться с 32-разрядную границу.

## <a name="see-also"></a>См. также

[Типы и хранилище](../build/types-and-storage.md)