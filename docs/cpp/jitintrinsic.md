---
title: jitintrinsic | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f8b1c932f53651b8ad116139724348714b183506
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939394"
---
# <a name="jitintrinsic"></a>jitintrinsic
Помечает функцию как значимую для 64-разрядной среды CLR. Этот модификатор используется с определенными функциями в библиотеках Microsoft.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__declspec(jitintrinsic)  
```  
  
## <a name="remarks"></a>Примечания  
 Ключевое слово `jitintrinsic` добавляет MODOPT (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>) к сигнатуре функции.  
  
 Пользователям не рекомендуется применять этот **__declspec** модификатор, как непредвиденные результаты могут возникать.  
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)