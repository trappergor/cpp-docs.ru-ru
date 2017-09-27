---
title: "Устаревшие соглашения о вызовах | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __fortran
- __pascal
- __syscall
dev_langs:
- C++
helpviewer_keywords:
- WINAPI
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
caps.latest.revision: 7
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
ms.openlocfilehash: 90f328552677bc0f41accc316433365467dd7673
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="obsolete-calling-conventions"></a>Устаревшие соглашения о вызовах
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 **__Pascal**, **__fortran**, и **__syscall** соглашения о вызовах, больше не поддерживаются. Их функциональные возможности можно эмулировать с помощью одного из поддерживаемых соглашений о вызовах и соответствующих параметров компоновщика.  
  
 WINDOWS. Теперь поддерживает H **WINAPI** макросом, который преобразуется в соответствующее соглашение о вызовах для целевого объекта. Используйте **WINAPI** где использовалась ранее **PASCAL** или **__far \__pascal**.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Передача аргументов и соглашения об именовании](../cpp/argument-passing-and-naming-conventions.md)
