---
title: "jitintrinsic | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- jitintrinsic
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6712a62aaff0ff903117da87364cae5bc88580fd
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="jitintrinsic"></a>jitintrinsic
Помечает функцию как значимую для 64-разрядной среды CLR. Этот модификатор используется с определенными функциями в библиотеках Microsoft.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__declspec(jitintrinsic)  
```  
  
## <a name="remarks"></a>Примечания  
 Ключевое слово `jitintrinsic` добавляет MODOPT (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>) к сигнатуре функции.  
  
 Применять этот модификатор `__declspec` пользователям не рекомендуется, поскольку это может привести к непредсказуемым результатам.  
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
