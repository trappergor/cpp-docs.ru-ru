---
title: Неустранимая ошибка NMAKE U1087 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1087
dev_langs:
- C++
helpviewer_keywords:
- U1087
ms.assetid: 5236ab54-e117-484d-99c3-852b061fd3d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f07309c64066b0a17aab110035c700c229c439df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319726"
---
# <a name="nmake-fatal-error-u1087"></a>Неустранимая ошибка NMAKE U1087
не может иметь: и:: зависимые объекты для того же целевого объекта  
  
 Целевой объект не может указываться в обоих с одинарным двоеточием (**:**) и двойным двоеточием (`::`) зависимостей.  
  
 Чтобы задать целевой объект в нескольких блоках описания, используйте `::` в каждой строке зависимости.