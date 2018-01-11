---
title: "Ошибка компилятора C2212 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2212
dev_langs: C++
helpviewer_keywords: C2212
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0c49161940c1f382a8bf9d82a648cc4396a11e86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2212"></a>Ошибка компилятора C2212
«Идентификатор»: __based недоступен для указателей на функции  
  
 Указатели на функции не могут объявляться `__based`. Если требуются данные на основе кода, используйте `__declspec` ключевое слово или `data_seg` pragma.