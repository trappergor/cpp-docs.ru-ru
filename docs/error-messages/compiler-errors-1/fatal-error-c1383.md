---
title: "Неустранимая ошибка C1383 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1383
dev_langs:
- C++
helpviewer_keywords:
- C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ff620211470e82cd53a893bdee94fb1ca5d405c9
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1383"></a>Неустранимая ошибка C1383
Параметр компилятора /GL несовместим с установленной версией среды CRL  
  
 Ошибка C1383 происходит, когда вы используете предыдущую версию среды CLR с более новой версией компилятора и когда вы компилируете с параметрами **/clr** и **/GL.**  
  
 Для устранения этой ошибки не используйте параметры **/GL** и **/clr** или установите версию среды CLR, которая поставляется с вашим компилятором.  
  
 Дополнительные сведения см. в разделах [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) и [/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md).
