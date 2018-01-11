---
title: "Неустранимая ошибка NMAKE U1087 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1087
dev_langs: C++
helpviewer_keywords: U1087
ms.assetid: 5236ab54-e117-484d-99c3-852b061fd3d0
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f70d63a0161885c6286714b2c860c778d9598c34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1087"></a>Неустранимая ошибка NMAKE U1087
не может иметь: и:: зависимые объекты для того же целевого объекта  
  
 Целевой объект не может указываться в обоих с одинарным двоеточием (**:**) и двойным двоеточием (`::`) зависимостей.  
  
 Чтобы задать целевой объект в нескольких блоках описания, используйте `::` в каждой строке зависимости.