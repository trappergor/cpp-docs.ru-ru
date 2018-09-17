---
title: Битовые поля | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- bitfields
ms.assetid: e9a1010d-1e1b-487f-9943-3c574e08f544
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7451ea6afee81cc296fb091705bde48041ef5d1
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722492"
---
# <a name="bitfields"></a>Разряды

Структура битовых полей ограничен 64 бита и может иметь тип автоматический int, int без знака, int64 или int64 без знака. Битовые поля, которые пересекают границу типа будет пропускать биты, чтобы выровнять битовое поле, чтобы далее выравнивание типа. Например целое число битовые поля не может пересекаться с 32-разрядную границу.

## <a name="see-also"></a>См. также

[Типы и хранилище](../build/types-and-storage.md)