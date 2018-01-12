---
title: "Ошибка средств компоновщика LNK2008 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2008
dev_langs: C++
helpviewer_keywords: LNK2008
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a7c2fecff55677653c25c7d87fb22fa984526159
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2008"></a>Ошибка средств компоновщика LNK2008
Целевой объект адресной привязки не выравнивается 'symbol_name'  
  
 Удалось найти целевой объект адресной привязки в объектном файле, которая не была правильно выровнена.  
  
 Эта ошибка может быть вызвана выравниванием пользовательского (например, #pragma [пакет](../../preprocessor/pack.md)), [выравнивание](../../cpp/align-cpp.md) модификатор, или с помощью кода, изменяющего выравниванием.  
  
 Если код не использует любой из указанных выше, это может быть вызвано компилятор.