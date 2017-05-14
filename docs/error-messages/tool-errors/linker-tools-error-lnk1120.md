---
title: "Ошибка средств компоновщика LNK1120 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1120
dev_langs:
- C++
helpviewer_keywords:
- LNK1120
ms.assetid: 56aa7d36-921f-4daf-b44d-cca0d4fb1b51
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 1809ed4e5950165d6a187fd3c62871c25124663f
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

---
# <a name="linker-tools-error-lnk1120"></a>Ошибка средств компоновщика LNK1120
*номер* неразрешенные внешние элементы  
  
Ошибка LNK1120 сообщает число (*номер*) ошибок неразрешенный внешний символ для этой операции связывания. Большинство неразрешенный внешний символ ошибки отображаются отдельно по [Ошибка средств компоновщика LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md) и [Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md), который предшествовать это сообщение об ошибке один раз для каждого неразрешенный внешний символ ошибки.  
  
Чтобы устранить эту ошибку, исправьте все остальные неразрешенные внешние ошибки или другие ошибки компоновщика, расположенные перед ним в выходные данные построения. Эта ошибка не указывается, когда остается без неразрешенные внешние ошибок.  

