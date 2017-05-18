---
title: "Предупреждение программы NMAKE U4010 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U4010
dev_langs:
- C++
helpviewer_keywords:
- U4010
ms.assetid: 99d8eb9a-ae31-40d1-b8c5-8c66732127d3
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 23feafbf82328ab2fe1a1d20a565432681ab6dab
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="nmake-warning-u4010"></a>Предупреждение программы NMAKE U4010
«целевой объект»: построение выполнить не удалось; Указан, продолжение...  
  
 Команда в блоке команд для данного целевого объекта вернула ненулевой код выхода. Параметр /K дал NMAKE продолжать обработку несвязанных частей построения и вывести код выхода 1 при окончании сеанса NMAKE.  
  
 Если данный целевой объект сам по себе, является зависимостью для другого целевого объекта, NMAKE выдает предупреждение [U4011](../../error-messages/tool-errors/nmake-warning-u4011.md) после этого предупреждения.
