---
title: Ошибка средств компоновщика LNK2008 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2008
dev_langs:
- C++
helpviewer_keywords:
- LNK2008
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4ee6a8a4c4cc6d33f47d5335daa9fccd4e5fd99
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299569"
---
# <a name="linker-tools-error-lnk2008"></a>Ошибка средств компоновщика LNK2008
Целевой объект адресной привязки не выравнивается 'symbol_name'  
  
 Удалось найти целевой объект адресной привязки в объектном файле, которая не была правильно выровнена.  
  
 Эта ошибка может быть вызвана выравниванием пользовательского (например, #pragma [пакет](../../preprocessor/pack.md)), [выравнивание](../../cpp/align-cpp.md) модификатор, или с помощью кода, изменяющего выравниванием.  
  
 Если код не использует любой из указанных выше, это может быть вызвано компилятор.