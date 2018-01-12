---
title: "Неустранимая ошибка C1383 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1383
dev_langs: C++
helpviewer_keywords: C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 24e9d7652c96c84f94bafbf2c808f2e5430037b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1383"></a>Неустранимая ошибка C1383
параметр компилятора /GL несовместим с установленной версией среды CRL  
  
 Ошибка C1383 происходит, когда вы используете предыдущую версию среды CLR с более новой версией компилятора и когда вы компилируете с параметрами **/clr** и **/GL.**  
  
 Для устранения этой ошибки не используйте параметры **/GL** и **/clr** или установите версию среды CLR, которая поставляется с вашим компилятором.  
  
 Дополнительные сведения см. в разделах [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) и [/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md).