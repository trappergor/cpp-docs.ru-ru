---
title: Предупреждение программы NMAKE U4011 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U4011
dev_langs:
- C++
helpviewer_keywords:
- U4011
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af9c0f90c507eebe212a9c3cbfb2f2d21cded43d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-warning-u4011"></a>Предупреждение программы NMAKE U4011
«целевой объект»: не все зависимые компоненты; целевой объект не построен  
  
 Зависимый данный целевой объект не существует или устарела, и команда обновления вернула ненулевой код выхода. Параметр /K дал NMAKE продолжать обработку несвязанных частей построения и вывести код выхода 1 при окончании сеанса NMAKE.  
  
 Это предупреждение предшествует предупреждение [U4010](../../error-messages/tool-errors/nmake-warning-u4010.md) для каждой зависимости, которую не удалось создать или обновить.