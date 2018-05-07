---
title: Битовые поля | Документы Microsoft
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
ms.openlocfilehash: 85db49f138cc733326e47a3008e79bae5ab4b7cb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="bitfields"></a>Разряды
Структура битовых полей ограничен 64 бита и может иметь тип со знаком int, int без знака, int64 или int64 без знака. Битовые поля, которые пересекают границу типа пропустит биты, чтобы выровнять разряды до следующего тип выравнивания. Например целое число со знаком битовые поля не может пересекаться с 32-разрядную границу.  
  
## <a name="see-also"></a>См. также  
 [Типы и хранилище](../build/types-and-storage.md)