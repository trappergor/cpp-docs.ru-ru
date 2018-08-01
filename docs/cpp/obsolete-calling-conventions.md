---
title: Устаревшие соглашения о вызовах | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __fortran
- __pascal
- __syscall
dev_langs:
- C++
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 922103e808541e2829350749a04d6004ba36577f
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403424"
---
# <a name="obsolete-calling-conventions"></a>Устаревшие соглашения о вызовах
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 **__Pascal**, **__fortran**, и **__syscall** соглашения о вызовах больше не поддерживаются. Их функциональные возможности можно эмулировать с помощью одного из поддерживаемых соглашений о вызовах и соответствующих параметров компоновщика.  
  
 \<Windows.h > теперь поддерживает макрос WINAPI, которая преобразуется в соответствующее соглашение о вызовах для целевого объекта. Использовать WINAPI, где вы ранее использовали PASCAL или **__far \__pascal**.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Передача аргументов и соглашения об именовании](../cpp/argument-passing-and-naming-conventions.md)