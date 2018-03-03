---
title: "Битовые поля | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- bitfields
ms.assetid: e9a1010d-1e1b-487f-9943-3c574e08f544
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 231d84e5d99cd9e6c1238ae12c143636f62ce80d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="bitfields"></a>Разряды
Структура битовых полей ограничен 64 бита и может иметь тип со знаком int, int без знака, int64 или int64 без знака. Битовые поля, которые пересекают границу типа пропустит биты, чтобы выровнять разряды до следующего тип выравнивания. Например целое число со знаком битовые поля не может пересекаться с 32-разрядную границу.  
  
## <a name="see-also"></a>См. также  
 [Типы и хранилище](../build/types-and-storage.md)