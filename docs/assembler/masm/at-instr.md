---
title: '@InStr | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- '@InStr'
dev_langs:
- C++
helpviewer_keywords:
- '@InStr symbol'
ms.assetid: 980d5b9f-2b88-4306-8955-df6cd2133e68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0fb92987de21f653440d6c4cc23d726ad323b69
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="instr"></a>@InStr
Макрос функцию, которая находит первое вхождение *string2* в *string1*, начиная с *позиции* в *string1*. Если *позиции* не отображается, поиск начинается с начала *string1*. Возвращает целочисленный позиции или 0, если *string2* не найден.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
@InStr( [[position]], string1, string2 )  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по символам](../../assembler/masm/symbols-reference.md)