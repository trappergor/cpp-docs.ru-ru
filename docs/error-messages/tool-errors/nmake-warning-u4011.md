---
title: "Предупреждение программы NMAKE U4011 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U4011
dev_langs: C++
helpviewer_keywords: U4011
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e2e922bbb07574774762f5800faa95d21357ccff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="nmake-warning-u4011"></a>Предупреждение программы NMAKE U4011
«целевой объект»: не все зависимые компоненты; целевой объект не построен  
  
 Зависимый данный целевой объект не существует или устарела, и команда обновления вернула ненулевой код выхода. Параметр /K дал NMAKE продолжать обработку несвязанных частей построения и вывести код выхода 1 при окончании сеанса NMAKE.  
  
 Это предупреждение предшествует предупреждение [U4010](../../error-messages/tool-errors/nmake-warning-u4010.md) для каждой зависимости, которую не удалось создать или обновить.